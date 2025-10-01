# Getting the code running
Download Docker for your desktop. Once it is installed, verify that it is properly installed by running the following command
```
docker --version
```
If you are on a Mac and this command has failed, you may need to create a symbolic link from the `/Applications` folder as
```
ln -s /Applications/Docker.app/Contents/Resources/bin/docker /usr/local/bin/docker
```
# Install the Docker image
At the command line, run the following command
```
docker pull ghcr.io/jorgensd/dolfinx-tutorial:release
```
# Run the Docker image
Navigate to a folder where you have relevant local FEM files.
```
cd ~/Documents
# Clone this github repository
cd comp_pdes_osu
```
From your `comp_pdes_osu` folder, launch the Docker container.
```
docker run -it --rm -p 8888:8888 -v $(pwd):/workspace -w /workspace ghcr.io/jorgensd/dolfinx-tutorial:release
```
This will start a Jupyter server. You can navigate to it by finding the relevant link in the terminal output that looks like this:
```
http://127.0.0.1:8888/lab?token=...
```
The modifications you make in `/workspace` in the Docker image are saved locally on your machine in `comp_pdes_osu` folder.
