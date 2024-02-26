# Subway-surfers-code
A little code thingy for subway surfers that chat gpt did for python don't know if it works tho and this is just a little thing
import pygame
import sys

# Initialize Pygame
pygame.init()

# Set up the screen
screen_width = 800
screen_height = 600
screen = pygame.display.set_mode((screen_width, screen_height))
pygame.display.set_caption("Subway Surfers Lite")

# Set up the character
character_width = 50
character_height = 50
character_x = 100
character_y = screen_height - character_height - 10
character_speed = 5

# Set up colors
white = (255, 255, 255)

# Main game loop
clock = pygame.time.Clock()

while True:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()

    # Move the character
    keys = pygame.key.get_pressed()
    if keys[pygame.K_LEFT] and character_x > 0:
        character_x -= character_speed
    if keys[pygame.K_RIGHT] and character_x < screen_width - character_width:
        character_x += character_speed

    # Draw everything
    screen.fill(white)
    pygame.draw.rect(screen, (0, 128, 255), (character_x, character_y, character_width, character_height))

    # Update the display
    pygame.display.flip()

    # Cap the frame rate
    clock.tick(30)
