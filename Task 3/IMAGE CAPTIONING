from transformers import BlipProcessor, BlipForConditionalGeneration
from PIL import Image

# Load model
processor = BlipProcessor.from_pretrained(
    "Salesforce/blip-image-captioning-base"
)

model = BlipForConditionalGeneration.from_pretrained(
    "Salesforce/blip-image-captioning-base"
)

# Image path
image = Image.open("image.jpg").convert("RGB")

# Process image
inputs = processor(image, return_tensors="pt")

# Generate caption
output = model.generate(**inputs)

caption = processor.decode(output[0], skip_special_tokens=True)

print("Generated Caption:")
print(caption)
