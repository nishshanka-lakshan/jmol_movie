after running the code and create every frames you need to run 


ffmpeg -framerate 10 -pattern_type glob -i "mo_*.png" -pix_fmt yuv420p mo_movie.mp4

Or 

ffmpeg -framerate 10 -pattern_type glob -i "mo_*.png" -c:v libx264 -pix_fmt yuv420p animation.mp4
