# Shift Operation CUDA Implementation

created by Peter Jin . readme written by [Alvin Wan](http://alvinwan.com)

# Installation

> If you have included this `shift` repository as a submodule in a separate repository, feel free to skip down to step 5.

1. If you have not already, setup a virtual environment with Python3, and activate it.

```
virtualenv shift --python=python3
source shift/bin/activate
```

Your prompt should now be prefaced with `(shift)`, as in

```
(shift) [user@server:~]$ 
```

2. Install `pytorch` and `torchvision`. Access [pytorch.org](http://pytorch.org), scroll down to the "Getting Started" section, and select the appropriate OS, package manager, Python, and CUDA build. For example, selecting Linux, pip, Python3.5, and CUDA 8 gives the following, as of the time of this writing

```
pip3 install http://download.pytorch.org/whl/cu80/torch-0.3.0.post4-cp35-cp35m-linux_x86_64.whl 
pip3 install torchvision
```

3. Clone this repository.

```
git clone git@github.com:peterhj/shiftnet_cuda_v2.git
```

4. `cd` into the root of this repository.

```
cd shiftnet_cuda_v2
```

5. Install the Python requirements for this package.

```
pip3 install -r requirements.txt
```

6. Compile the Shift Layer implementation in C.

```
make
```

> **Getting `invalid_device_function`?** Update the architecture code in [`models/shiftnet_cuda_v2/Makefile`](https://github.com/alvinwan/shiftresnet-cifar/blob/master/models/shiftnet_cuda_v2/Makefile#L4), currently configured for a Titan X. e.g., A Tesla K80 is `sm-30`.

Your custom CUDA layer is now installed.
