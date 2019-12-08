# GitHub Pages Custom Domain

This repository contains a step-by-step guide on how to set up a custom domain with GitHub Pages.

This is documented in the official GitHub docs, but I always hate refreshing my memory on it there, because it's too long-winded.

These steps are what I am using, they may not be complete for your scenario, or may be straight up wrong.
It's certainly incomplete, todoes are below.

Also, **important note**: GitHub Pages do not support IPv6, which is just so amateur of GitHub I don't even want to think about it.
So **do not** ever use GitHub Pages for anything important, because until IPv6 support is added, GitHub Pages are not sufficient.

I am setting up just APEX domains, because WWW domains feel super nineties to me.
I might try to set it up so that both APEX and WWW are supported one day, but definitely not this weekend.

1. Add an `A` record for `185.199.108.153` with your domain registrar

   Feel free to add all four, I think this is for redundancy / load balancing, but I don't know enough about DNS to really know.
   Also, like I already stated, GitHub Pages is a toy and should not be used for anything even remotely serious,
   so if adding just one `A` record jeopardizes your site's availability, it's kind of a good thing as it will keep you reminded.

2. Delete `AAA` records otherwise visitors accessing with IPv6 will see some bullshit

   Again, I don't know enough about HTTPS to really know how or why this happens, but it happened to me.

3. Go to repository settings and enable GitHub Pages

   It doesn't matter if you serve from the root directory of the repository, from `docs` or the `gh-pages` branch.

4. Enter your custom domain and save

   Do not check *Enforce HTTPS* at this stage yet, GitHub won't allow you anyway until the DNS records have propagated.

5. Wait for the DNS records to propagate

   This is going to take like half an hour to an hour, but it can take significantly longer as well.

6. Check *Enforce HTTPS* and save

7. Verify the HTTPS connection is enforced

   This will take a while and you might need to flush your browser's cache a few times.

## To-Do

### See if both WWW and APEX domain setup is possible
