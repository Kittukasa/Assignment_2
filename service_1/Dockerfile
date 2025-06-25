# Use official Golang image as builder
FROM golang:1.21-alpine

# Set working directory inside container
WORKDIR /app

RUN apk add --no-cache curl
# Copy the single Go source file into the container
COPY main.go .

# Build the Go binary (named 'app')
RUN go build -o app main.go

# Command to run when container starts
CMD ["./app"]
