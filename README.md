# geni-rspecs

GENI RSpecs

## Create an image on APT

APT is not (technically) an InstaGENI rack so the "Snapshot" button is not
active. To take a snapshot you have to go straight to the URL that
the snapshot button composes for you. To do that you need three pieces of
information:

1. Slice ID (`slice_id`)
2. Aggregate Manager ID (`am_id`)
3. Sliver ID (`sliver_id`)

The general form of the URL is:

    ```
    createimage.php?slice_id=SLICE_ID&am_id=AM_ID&sliver_id=SLIVER_ID
    ```

### Finding Slice ID

Go to the slice page on the portal, and copy the `slice_id` argument
in the URL in your web browser.

### Finding Aggregate Manager ID

Go to the slice page and choose the aggregates tab. Move the pointer
over an aggregate in the right hand panel (note: you have to have
resources to see any aggregates in the panel). Then click on
"Resource Details" to go to the details page. Copy the AM ID from that
URL.

### Finding Sliver ID

Stay on the details page. At the bottom, click the
"Show Raw XML Resource Specification (Manifest)" link. This will display
the manifest RSpec at this AM. Find the node you want to snapshot, maybe
by the client_id attribute. That node will also have a sliver_id
attribute that contains the URN of this specific node (i.e. sliver) at
the aggregate.
