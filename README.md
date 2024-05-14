This repo contains a modified example of bevy live asset reload feature and shows the issue 
where bevy does not pick up changes in a blender file due to how blender saves the file and notify debounces the file system events.

To repro:
```shell
RUST_LOG=trace cargo run 2>&1 | grep test.blend
# then open test.blend in blender and save it
```
Observe `assets/processed` lacking `test.blend` while it should be there.
