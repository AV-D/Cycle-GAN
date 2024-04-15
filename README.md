# CycleGAN for Monet to Real Image Translation

This project uses a CycleGAN, a type of Generative Adversarial Network (GAN), to translate images from the style of Monet paintings to realistic photographs, and vice versa. CycleGANs are notable for their ability to perform image-to-image translation without the need for paired examples, making them ideal for tasks such as artistic style transfer.

## Theory Behind CycleGAN

CycleGAN involves two generators and two discriminators:

- **Generators (G_AB and G_BA):** Translate images from domain A to B and vice versa. They include convolutional layers, downsampling, residual blocks, and upsampling layers.
- **Discriminators (D_A and D_B):** Distinguish between real images and translated images in each domain, using convolutional layers that progressively downsample the input.

### Loss Functions

- **Adversarial Loss:** Ensures the generated images are indistinguishable from real images in the target domain.
- **Cycle Consistency Loss:** Preserves content by requiring that an image translated to another domain and back again should approximate the original image.
- **Identity Loss:** Encourages the generator to act as an identity function when real images from the target domain are used as input.

## Project Description

This project applies CycleGAN to translate between Monet paintings (domain A) and real landscape photos (domain B), using a dataset of unpaired images.

### Implementation Details

- **Data Preparation:** Images are resized, randomly cropped, normalized, and augmented with random horizontal flips.
- **Model Architecture:** Custom Generator and Discriminator networks with specific configurations for weight initialization and residual blocks.
- **Training:** Uses alternating updates to the generators and discriminators with specific hyperparameters, including learning rates and loss weights (lambda_cyc and lambda_id).
- **Evaluation:** Demonstrated through generated, translated, and reconstructed images to evaluate cycle consistency.

## Usage

1. **Installation:**
   - Ensure all dependencies are installed, including PyTorch, torchvision, PIL, and torch_snippets.
2. **Dataset:**
   - Organize Monet paintings and real images into separate directories within a dataset folder.
3. **Training:**
   - Run the training script, adjusting hyperparameters as needed.
4. **Evaluation:**
   - Use the provided functions to generate and visualize translated and reconstructed images.

## Technologies Used

- **PyTorch:** For model implementation and training.
- **torchvision:** For image transformations.
- **PIL:** For image loading and processing.
- **torch_snippets:** For utility functions.

## Acknowledgments

This project was inspired by the CycleGAN paper, "Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks" by Zhu et al. Implementation details and training strategies were adapted for translating between Monet paintings and real images.
