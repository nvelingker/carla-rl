FROM anibali/pytorch:1.5.0-cuda10.2

USER root
# Install vim for local development
RUN rm /etc/apt/sources.list.d/cuda.list
RUN rm /etc/apt/sources.list.d/nvidia-ml.list
RUN ["apt-get", "update"]
RUN ["apt-get", "install", "-y", "vim"]
RUN ["apt-get", "update"]
RUN ["apt-get", "install", "-y", "ffmpeg"]

# Add requirement.txt first for caching purposes.
COPY requirements.txt /app
RUN pip install -r requirements.txt

# Running a terminal lets you run any script.
CMD /bin/bash
