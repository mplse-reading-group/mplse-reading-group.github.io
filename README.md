## Modifying the Schedule
The schedule for each semester is stored in a markdown file in **schedules/**.

**Current state of affairs**:
Edit the html table, and commit those changes.
You can try to do this on the github web interface, which gives you a preview and basic html editor support.

**Wish**:
Edit the pipe table, and commit those changes.
You can do this on the github web interface, and it gives you a markdown preview.

The github workflow should automatically build and deploy the site at
<https://mplse-reading-group.github.io>
### Manual Intervention
#### Building the Site Manually
    cabal update
    cabal build
    cabal run -- site rebuild
#### Previewing Changes
    cabal run -- site watch --hostname HOSTNAME --port PORT
#### Deploying
The github workflow builds the site from *trunk* and copies the generated site contents from **docs/** to the branch *gh-pages*.
Github pages then serves *gh-pages*.

You could manually build the site and push to *gh-pages*.
(But the next push to *trunk* will probably overwrite whatever you did.)
