# My Blog

The code for my blog, this readme is mostly for myself for when I inevitably stop working on this blog for a bit and forget how I set it up.

## Notes

- After cloning this repo also need to run the following line to pull the submodules (hugo themes)

```bash
git submodule update --init --recursive
```

- Run the following to makes a new post, change the post's `title:` in the header, make sure the `draft:` tag in the header is set to false if the post is finished

```bash
hugo new content/posts/post???.md
```

- `hugo server` to test locally

- Site build happens through a github action, don't need to do hugo build locally before committing and pushing changes.

- Need to remember to change theme in the build action too if I change themes
