import pygame
import sys
import math

# Initialize Pygame
pygame.init()

# Set up display
width, height = 600, 400
screen = pygame.display.set_mode((width, height))
pygame.display.set_caption("Ball Spinning Game")

# Set up colors
white = (255, 255, 255)

# Set up ball
ball_radius = 20
ball_color = (0, 128, 255)
ball_speed = 5
angle = 0

# Set up clock
clock = pygame.time.Clock()

while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    # Clear the screen
    screen.fill(white)

    # Calculate new position of the ball
    angle += 0.05
    x = width // 2 + int(math.cos(angle) * 100)
    y = height // 2 + int(math.sin(angle) * 100)

    # Draw the spinning ball
    pygame.draw.circle(screen, ball_color, (x, y), ball_radius)

    # Update the display
    pygame.display.flip()

    # Cap the frame rate
    clock.tick(60)

