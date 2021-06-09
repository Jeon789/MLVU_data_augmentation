# MLVU_data_augmentation

# This is for fine-tuning of trained ResNet with CIFAR-10
- Data is augmented as changing background with RGB
- Keep in mind that batch_size = 100 is fixed through out this task
- So, the train set = 500 * 100 * 32 * 32 * 32 ( or 500 * 100 * 3 * 32 * 32) , test set = 100 * 100 * 32 * 32 * 3 ( or 100 * 100 * 3 * 32 * 32 )
