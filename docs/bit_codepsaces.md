# Setup Bit on GibHub Codespaces

I bought an iPad Pro M1 recently, and set on using it for FE Dev, I embarked on a mission to get Bit working on Codespaces, but came across several issues. The following is a guide of how I accomplished to get it working — thanks to the persistance of my colleague @cerqueira 

## Requirements
- Repo access
- Keyboard and Mouse for iPad
- GitHub Codepsaces access
- Bit access
- SSH key (will cover this)
- Login to Bit
- Run your project!

## Setup

### Repo access

This is pretty straight forward, but I assume having the right permissions could be an issue. In other words, make sure you have Write, Maintain or Admin permissions, before getting started.

### Keyboard and Mouse for iPad

This is key at the very least for setup. Otherwise this will be a pretty frustrating experience.

### GitHub Codespaces access

In order to get Codespaces access you might need your Org admin to provide it to you. In my case, the following Codespaces option was not showing:

If you face a similar issue, I believe this documentation should help.

**Important:** When you first run VS Code on the iPad, you may experience a GPU Acceleration bug, where the terminal will not display any text — although it may be working. You can solve this issue by adding a line to your settings file:

	"terminal.integrated.gpuAcceleration": "off"

### Install Bit

You should be able to install Bit as instructed by [Bit’s documentation](https://harmony-docs.bit.dev/getting-started/installing-bit).

A very important thing to know is that you must have node version 12 and up (you should be able to manage the version as you would elsewhere: nvm). A quick summary:

1. Install BVM
2. Install Bit

### Bit access

Again, this is not rocket science, as you will obviously need access to Bit for this setup, as you will need in any other Dev environment.

Make sure you have Admin or Developer access. Viewer will probably only give you limited access — or not work.

### Login to Bit

Run the `bit login` command. This will open a browser window, and it will fail. Do the following:

1. Go to your "Ports" tab, on the bottom of your screen
2. Copy the URL of the single port you should have open
3. Go back to the Bit login screen that failed earlier
4. Replace the 127.0.0.1 IP address for the address you copied on step 2 (including the port number)
5. Login to Bit (unless you already have an active session on the browser, and you might get you logged in automagically)

### Run your project!

At this point you should be ready to run the following commands to get Bit going:

1. `bit install`
2. `bit compile`
3. `bit start`

## Alternative methods of login

### SSH key

In order to get an SSH key, you will need to run a few commands to create an SSH key, and then add the key to your Bit account. Follow these steps:

1. Create the SSH key
2. Copy the public key
3. Add the SSH key to your Bit account
