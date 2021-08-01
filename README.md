# Pilot Waypoint

These contain the necessary binaries and Dockerfiles to build our custom Waypoint Server images.

You can also pull the images via Docker Hub: `pilotframework/pilot-waypoint:<tag>`

If you'd like to use our experimental development image on your Waypoint Server, you can:
- `pilot setup --(gcp || aws) --dev` via Pilot
- `waypoint install -accept-tos -platform=docker -docker-server-image=pilotframework/pilot-waypoint:<tag>` via Waypoint