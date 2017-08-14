
## Setting up jekyll

Hello there! 

I am very excited to start my site using Jekyll! I was going to use wordpress to develop and host my site. But just this morning, I read Andrej Karpathy's [post](http://karpathy.github.io/2014/07/01/switching-to-jekyll/) on switching from Wordpress to Jekyll and I was sold. True, the themes are very simple and minimalistic but as a developer that's the kind of theme I was looking for! so here I am here with my first post on the installation of Jekyll. The installation steps are very simple but I did face certain challenges when I was installing, so this post is for those who decide to use Jekyll and face similar issues.

The steps I followed are originally from [Jekyll site](http://jekyllrb.com/)
To start off
```
gem install jekyll
```
The issue you might face:<br>
    No write permissions
    
  Fix:<br>
    use sudo-<br>
    ```
    sudo gem install jekyll
    ```
    
    Issue you might face:<br>
      ruby version required >=2.1.0 ( Mine was 2.0.0 )
   
   Fix:<br>
   ```
        brew update ruby
        brew link ruby
   ```
     
   Issue you might face:
         
   Error: Could not symlink lib/pkgconfig/ruby-2.4.pc
   /usr/local/lib/pkgconfig is not writable.
          
   Fix:
    
        sudo chown -R $(whoami) /usr/local/lib/pkgconfig
    
   and then run the command "brew link ruby"
Finally use 
  ```
  sudo gem install jekyll
  ```
  
Once you are done with this, you can go to your github account, create a new repository called <username>.github.io and commit the folder contents there. 
Then go to about.md and add what you would like your site's about page to show. 
And then go to _config.yml and customize it according to your needs. Finally, you can goto _posts folder and create md files with name starting with the current date such as '2017-08-13-Jekyll-install.md'
