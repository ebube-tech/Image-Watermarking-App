from PIL import Image, ImageDraw, ImageFont

def add_watermark(input_image_path, output_image_path, text):
    original_image = Image.open(input_image_path)
    width, height = original_image.size
    transparent = Image.new('RGBA', (width, height), (255, 255, 255, 0))
    transparent.paste(original_image, (0,0))
    draw = ImageDraw.Draw(transparent)
    text_width, text_height = draw.textsize(text)
    margin = 10
    x = width - text_width - margin
    y = height - text_height - margin
    font = ImageFont.truetype('arial.ttf', 36)
    draw.text((x, y), text, font=font, fill=(255, 255, 255, 128))
    transparent.save(output_image_path)

if __name__ == '__main__':
    input_image_path = 'input.jpg'
    output_image_path = 'output.png'
    text = 'Watermarked'
    add_watermark(input_image_path, output_image_path, text)
