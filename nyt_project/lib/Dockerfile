# Use the official Flutter image as the base image
FROM cirrusci/flutter:stable AS build

WORKDIR /app

COPY pubspec.* ./

RUN flutter pub get

COPY . .

# Build the Flutter app for release
RUN flutter build apk --release

FROM nginx:alpine

# Copy the built Flutter app from the previous stage
COPY --from=build /app/build/app/outputs/flutter-apk/app-release.apk /usr/share/nginx/html/app-release.apk

EXPOSE 8080

# Start Nginx and serve the Flutter app
CMD ["nginx", "-g", "daemon off;"]

# run with "docker build -t flutter-app ."
