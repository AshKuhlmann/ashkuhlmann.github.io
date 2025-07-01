# ashkuhlmann.github.io
Sharing my learning process, projects, and certifications as I transition into a career in IT — with a focus on help desk, Linux systems, and eventually cloud and DevOps.

## Run Website Locally
If you're using the Bash shell, you'll need to edit a different file. Instead of `.zshrc`, you should use `.bash_profile`.

Here are the corrected steps for a Bash user on an M-series Mac.

-----

### 1\. Configure Your Bash Profile

Open the Terminal and run this command to add the Homebrew Ruby path to your `.bash_profile`:

```bash
echo 'export PATH="/opt/homebrew/opt/ruby/bin:$PATH"' >> ~/.bash_profile
```

This ensures that your terminal will use the Ruby version installed by Homebrew.

-----

### 2\. Restart Your Terminal

For the changes to take effect, you must **quit the Terminal app completely** and open a new window.

To confirm that you're using the correct Ruby version, run:

```bash
ruby -v
```

The output should now show a version number like `3.x.x`.

-----

### 3\. Install Jekyll and Bundler

Now that your environment is correctly configured, you can install Jekyll and Bundler again.

```bash
gem install bundler jekyll
```

This should now complete without any errors.

-----

### 4\. Run the Local Server

Finally, navigate to your project's root folder in the terminal and start the server:

```bash
bundle exec jekyll serve
```

You can now view your site at **[http://localhost:4000](https://www.google.com/search?q=http://localhost:4000)**.
