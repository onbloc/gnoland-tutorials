# Build the Local Testnet

### Step 1. Build the Gno Project

Change your working directory to `gno/gno.land`.

```bash
$ cd ~/gno/gno.land/
```

Use the `make` command to build the gnoland binary.

```bash
$ make install.gnoland
```

<figure><img src="../../.gitbook/assets/2-5.png" alt=""><figcaption></figcaption></figure>

> **Note:** If you're developing on a Windows device, install the GNU make using this [link](https://gnuwin32.sourceforge.net/packages/make.htm).


### Step 2. Run a Local Node

Start a local Gnoland blockchain node with the following command:

```bash
$ gnoland
```

<figure><img src="../../.gitbook/assets/05_run_gnoland.png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../.gitbook/assets/06_follow_gnoland.png" alt=""><figcaption></figcaption></figure>

After a few moments, you will start to see blocks being produced on your network.

### Step 3. Build a Web Page (Optional)

This section will teach you how to launch your own gno.land web page that will serve as a docs page for your network. Although this section is optional, we highly recommend completing it.

First, build the web page with the following command:

```
$ make install.gnoweb
```

Then, run the web page with the following command:

```
$ gnoweb
```

<figure><img src="../../.gitbook/assets/07_build_run_gnoweb.png" alt=""><figcaption></figcaption></figure>

To confirm that your web page is running on your network, use a browser to access the following link:

{% embed url="http://localhost:8888" %}

<figure><img src="../../.gitbook/assets/08_webpage.png" alt=""><figcaption></figcaption></figure>

Under the **Explore new packages.** section, you will see a list of pre-built realms and packages that are already deployed on your network. You may click on each one to view its details.
