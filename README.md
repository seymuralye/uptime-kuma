# Uptime Kuma Custom Docker Build

<p>This repository contains a custom Dockerfile for building and running <strong>Uptime Kuma</strong> with necessary fixes.</p>

<h2>How to Build and Run</h2>

<h3>1. Build the Docker Image</h3>
<p>Run the following command to build the custom Docker image:</p>
<pre><code>docker build -t uptime-kuma-fixed .</code></pre>
<p><strong>Explanation:</strong> <code>-t uptime-kuma-fixed</code> tags the image as <code>uptime-kuma-fixed</code>.</p>

<h3>2. Run the Docker Container</h3>
<p>Use the following command to start the Uptime Kuma container:</p>
<pre><code>
docker run -d \
  --name uptime-kuma \
  -p 3001:3001 \
  -v uptime-kuma:/app/data \
  uptime-kuma-fixed
</code></pre>

<p><strong>Explanation:</strong></p>
<ul>
    <li><code>--name uptime-kuma</code>: Names the container <strong>uptime-kuma</strong>.</li>
    <li><code>-p 3001:3001</code>: Maps port <strong>3001</strong> on the host to port <strong>3001</strong> in the container.</li>
    <li><code>-v /var/lib/docker/volumes/uptime-kuma:/app/data</code>: Mounts the host directory <code>/var/lib/docker/volumes/uptime-kuma</code> to <code>/app/data</code> in the container for persistent data storage.</li>
    <li><code>uptime-kuma-fixed</code>: The name of the built Docker image.</li>
</ul>

<h3>3. Verify the Container</h3>
<p>Run the following command to ensure the container is up and running:</p>
<pre><code>docker ps</code></pre>
<p>You should see the container named <strong>uptime-kuma</strong> in the list of running containers.</p>

<h2>Notes</h2>
<ul>
    <li>Ensure the directory <code>/var/lib/docker/volumes/uptime-kuma</code> exists and has the correct permissions.</li>
    <li>If you encounter any issues, check the container logs using:</li>
</ul>
<pre><code>docker logs uptime-kuma</code></pre>
