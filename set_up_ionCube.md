To download and install the correct version of ionCube Loader, you'll first need to determine whether your operating system is 32-bit or 64-bit. Here's how you can do that, followed by the steps to download and install ionCube Loader for your system.

### Determine Your Operating System's Architecture

Run the following command on your VPS to check if your operating system is 32-bit or 64-bit:

```bash
uname -m
```

- If the output is `x86_64`, your system is 64-bit.
- If the output is `i686` or `i386`, your system is 32-bit.

### Download ionCube Loader

1. **Visit the ionCube Loader Downloads Page:**
   Go to the [ionCube Loader download page](https://www.ioncube.com/loaders.php).

2. **Download the Correct Loader:**
   - Since you're using a Linux server, download the version for Linux.
   - Choose the correct version based on the architecture of your operating system (32-bit or 64-bit).
   - For example, if your system is 64-bit, download the file named something like `ioncube_loaders_lin_x86-64.tar.gz`.

### Install ionCube Loader

1. **Upload the Downloaded File to Your Server:**
   If you downloaded the file to your local machine, use `scp` or another file transfer method to upload it to your server.

   Example using `scp`:

   ```bash
   scp /path/ioncube_loaders_lin_x86-64.tar.gz root@your_server_ip:/tmp
   ```

2. **Extract the Loader:**
   Connect to your server and extract the downloaded file:

   ```bash
   cd /tmp
   tar xzf ioncube_loaders_lin_x86-64.tar.gz
   ```

3. **Move the Loader to the Appropriate Directory:**
   Move the `ioncube_loader_lin_8.1.so` file to the PHP extension directory. This directory varies depending on your PHP version and operating system, but it's usually something like `/usr/lib/php/20210902/`.

   ```bash
   sudo mv ioncube/ioncube_loader_lin_8.1.so /usr/lib/php/20210902/
   ```

4. **Edit the PHP Configuration File:**
   Add the ionCube Loader to your PHP configuration file.

   ```bash
   sudo nano /etc/php/8.1/fpm/php.ini
   ```

   Add the following line at the end of the file:

   ```ini
   zend_extension = /usr/lib/php/20210902/ioncube_loader_lin_8.1.so
   ```

5. **Restart PHP-FPM:**
   Restart the PHP-FPM service to apply the changes:

   ```bash
   sudo systemctl restart php8.1-fpm
   ```

6. **Verify the Installation:**
   Create or access the `info.php` file you previously created to verify that ionCube Loader is now listed.

### Summary

By following these steps, you should be able to download and install the correct version of ionCube Loader for your system.