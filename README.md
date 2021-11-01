# scippneutron-benchmarks

Benchmarks are visible here: https://scipp.github.io/scippneutron-benchmarks/

Using ASV (http://github.com/airspeed-velocity/asv/) to perform benchmarks on the Scipp library.

This implementation of ASV assumes you have a copy of the scipp repository in a folder names "repo", so in order for this to run properly locally, like in our CI:

```bash
git clone https://github.com/scipp/scippneutron repo
```

Then you can setup your machine, currently we use the cloud-container as a name for the machine we use.

```bash
asv machine --machine cloud-container --os "Ubuntu latest" --arch 'x86_64' --cpu "2 Core CPU" --num_cpu 2 --ram '7GB'
```

Then we can run ASV to perform the benchmarks. You must have a C and C++ compiler that works with the current version of scipp, which can be found in the documentation (https://scipp.github.io/reference/developer/tooling.html)

```bash
asv run -m cloud-container -v -e
```

You can locally preview the benchmarks by first running a publish command, and then preview which will give you an IP that lets you look at benchmark:

```bash
asv publish
asv preview
```

