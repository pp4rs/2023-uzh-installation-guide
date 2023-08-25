# R

R is a language for statistical computing and graphics.
R's use in the data science and econometrics community has taken off over recent years and (at a bare minimum) should be considered as an open source replacement to Stata.

!!! Note "Department Managed Laptops"
        Once again, just go to the Software Center. On windows laptops just install R Studio since this will include R. On Mac, install R and RStudio individually.

## Installing R for Mac Users

Go to the [R homepage](https://cran.r-project.org/) and download the installer for your operating system.

The current version for Mac and Windows is `R version 4.3.1`.

Once you have installed R, [verify your install](#verifying-your-install-of-r).

!!! tip "Why Not Install via Homebrew?"
        There are conflicting views on Homebrew's installation of `R`.
        Because we haven't tried it to ensure no problems will emerge, we recommend going with the installation based on the CRAN distributed package.

## Installing R for Linux Users

First, we need to add a repository so that our operating system knows where to install the most recent version of `R` from.

Enter the following into the terminal and press `Return`:

```bash
wget -qO- https://cloud.r-project.org/bin/linux/ubuntu/marutter_pubkey.asc | sudo tee -a /etc/apt/trusted.gpg.d/cran_ubuntu_key.asc
sudo add-apt-repository "deb https://cloud.r-project.org/bin/linux/ubuntu $(lsb_release -cs)-cran40/"
```

Now, update to get the package manifests from the new repository:

```bash
sudo apt-get update
```

We can now install `R` as from the terminal by entering the following:

```{bash}
sudo apt-get install r-base r-base-dev
```

Install the multi-threaded OpenBlas library to get higher performance for linear algebra operations:

```{bash}
sudo apt-get install libopenblas-base
```

Now, [verify your install](#verifying-your-install-of-r).

<!-- !!! warning "R on WSL Ubuntu vs. R on native Windows"
        Even if you already have a version of `R` installed on your Windows machine, you need to install `R` inside the WSL Ubuntu environment we have set up.
        Your Ubuntu terminal cannot see everything you have on your native Windows installation. -->

## Installing R for Windows Users
We are installing R with winget:
```bash
winget install -e --id RProject.R
```
Now, [verify your install](#verifying-your-install-of-r).

## Verifying your Install of R 
Open a terminal and enter:

```bash
R --version
```

followed by pressing `Return`. The expected return begins with:

```bash
R version 4.2.x (2022-xx-xx) -- "Some Funky Name"
```

!!! warning "Failure"
        If this verification doesnt work, R has not been added to your PATH. This is no problem for us. Just check whether RStudio works after installing it in the next step.

