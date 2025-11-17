---
layout: base
title: Getting Starting
date: 2025-10-07
---

# Getting Started
Our base website template is called Xanthan. It's like a sourdough starter that's meant to spawn variants. But you probably only want to use a subset bit of Xanthan functionality for your site. To make things simpler and easier to learn, we've creeated a few different starter templates suited for common purposes.

There's nothing special about these templates other than they come with a few pages and navbars that suit the point of the template. You can edit everything later on---adding/renaming/deleting pages and folder, changing the navigation bar, adding images, and of course changing the text and style. 

This page specifies the steps necessary to create your own website, which  **takes about 10 minutes**.

<style>
.setup-selector {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 1rem;
  margin: 2rem 0;
}

.setup-option {
  padding: 1.5rem;
  border: 2px solid #ddd;
  border-radius: 8px;
  cursor: pointer;
  transition: all 0.3s ease;
  background: white;
}

.setup-option:hover {
  border-color: #666;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}

.setup-option.selected {
  border-color: var(--text-link, #007bff);
  background: var(--bg-secondary, #f8f9fa);
  box-shadow: 0 4px 12px rgba(0,123,255,0.2);
}

.setup-option input[type="radio"] {
  display: none;
}

.setup-option h3 {
  margin: 0 0 0.5rem 0;
  font-size: 1.2rem;
}

.setup-option p {
  margin: 0;
  color: #666;
  font-size: 0.9rem;
}

.template-name {
  font-weight: 600;
  color: var(--text-link, #007bff);
}

/* Responsive: stack on small screens */
@media (max-width: 768px) {
  .setup-selector {
    grid-template-columns: 1fr;
  }
}
</style>

<div class="setup-selector">
  <label class="setup-option selected" for="option-xanthan">
    <input type="radio" name="template" id="option-xanthan" value="xanthan" checked>
    <h3>Xanthan</h3>
    <p>The whole shebang. You'll get a copy of everything you see on this site.</p>
  </label>
  
  <label class="setup-option" for="option-portfolio">
    <input type="radio" name="template" id="option-portfolio" value="portfolio">
    <h3>Portfolio</h3>
    <p>Show off your work and interests</p>
  </label>
  
  <label class="setup-option" for="option-class-project">
    <input type="radio" name="template" id="option-class-project" value="class-project">
    <h3>Class Project</h3>
    <p>Gather and display student work for a collaborative project</p>
  </label>

  <label class="setup-option" for="option-scrollstory">
    <input type="radio" name="template" id="option-scrollstory" value="scrollstory">
    <h3>Scrollstory</h3>
    <p>A simple site for displaying a research story</p>
  </label>

</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
  const options = document.querySelectorAll('.setup-option');
  const radioButtons = document.querySelectorAll('input[name="template"]');
  
  // Template configuration
  const templates = {
    xanthan: {
      name: 'Xanthan',
      repo: 'amaranth-unm/xanthan',
      url: 'http://github.com/amaranth-unm/xanthan'
    },
    portfolio: {
      name: 'Portfolio',
      repo: 'amaranth-unm/portfolio-template',
      url: 'http://github.com/amaranth-unm/portfolio-template'
    },
    'class-project': {
      name: 'Class Project',
      repo: 'amaranth-unm/class-project-template',
      url: 'http://github.com/amaranth-unm/class-project-template'
    },
    'scrollstory': {
      name: 'Scrollstory',
      repo: 'amaranth-unm/scrollstory-template',
      url: 'http://github.com/amaranth-unm/scrollstory-template'
    }

  };
  
  // Add click handlers to option labels
  options.forEach(option => {
    option.addEventListener('click', function() {
      // Remove selected class from all options
      options.forEach(opt => opt.classList.remove('selected'));
      // Add selected class to clicked option
      this.classList.add('selected');
      
      // Get the selected value
      const selectedValue = this.querySelector('input[name="template"]').value;
      
      // Update content with selected template
      updateContent(selectedValue);
    });
  });
  
  function updateContent(templateKey) {
    const template = templates[templateKey];
    
    // Update template name
    document.querySelectorAll('.template-name').forEach(el => {
      el.textContent = template.name;
    });
    
    // Update repository link
    const repoLink = document.querySelector('.template-repo-link');
    if (repoLink) {
      repoLink.href = template.url;
      repoLink.textContent = template.name + ' repository';
    }
    
    // Update all repo references (lowercase for repository names)
    document.querySelectorAll('.template-repo-name').forEach(el => {
      el.textContent = template.name.toLowerCase();
    });
  }
  
  // Initialize with first option
  updateContent('xanthan');
});
</script>

### Create an account at GitHub
- Create an account at [GitHub](http://github.com/register). Whatever username you choose will be referred to below as GITHUB_USERNAME.
- Once you've gone through the confirmation process, make sure you are at your account home page. The URL will look like http://github.com/GITHUB_USERNAME.


### Make a copy of <span class="template-name">Xanthan</span>
Rather than create everything from scratch, let's start with a basic set of core files for your site.
- Go to the <a href="http://github.com/amaranth-unm/xanthan" class="template-repo-link">Xanthan repository</a>
- Click the green `Use this Template` button in the upper right.
- Name your repository (referred to as REPOSITORY below). You don't need to call it <span class="template-repo-name">xanthan</span>, and you can always rename it later (or delete it and start over).
- Click the green `Create Repository` button in the lower right.

### Confirm your config file
If you named your repository something other than <span class="template-repo-name">xanthan</span>, you need to make one small configuration edit. If you did not change <span class="template-repo-name">xanthan</span> to something else, skip this section.
- Click the `Code` tab near the top left
- Edit `_config.yml` file to have the same `baseurl` as your repository name. 
- Commit your change with the green Commit button.

### Enable GitHub Pages
Now that your have your starter files, we just need to tell GitHub that you want to use your repository to build a website.
- Click on the `Settings` tab in the upper right of the nav bar. 
- On the left, click the link for `Pages`.
- Near the top, under the Build & Deployment section, under `Source`, the `Deploy from a Branch` should be selected.
- Directly below, under `Branch`, change from `None` to `main`.
- Click the `Save` button that appears on that same line.
- Your site is now being built, and you can see the status via the `Actions` tab.
- After about a minute, reload the page and you'll see a link to your site.  
- The URL that appears there looks like: http://GIHUB_USERNAME.github.io/REPOSITORY/. For example, your final URL should look like http://fredgibbs.github.io/<span class="template-repo-name">xanthan</span>


{% include alert.html 
class="info"
title="Know your URLs"
text="Remember you have two (2!) important URLs to keep track of:
- Your REPOSITORY, which looks like [http://github.com/amaranth-unm/xanthan](http://github.com/amaranth-unm/xanthan)
- Your WEBSITE, which looks like [http://amaranth-unm.github.io/xanthan](http://amaranth-unm.github.io/xanthan)
"
%}


### Congratulations on your NEW WEBSITE!

Now you're ready to explore the components of your site and start editing. Let's start with [Understanding Folders](understanding-folders).