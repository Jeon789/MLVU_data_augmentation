# MLVU_data_augmentation

# This is for fine-tuning of trained ResNet with CIFAR-10
- Data is augmented as changing background with RGB
- Keep in mind that batch_size = 100 is fixed through out this task
- So, the train set = 500 * 100 * 32 * 32 * 32 ( or 500 * 100 * 3 * 32 * 32) , test set = 100 * 100 * 32 * 32 * 3 ( or 100 * 100 * 3 * 32 * 32 )


TrainSet 50000으로 학습시킨 Accuracy 88.49% 짜리 ResNet에다가
일일이 눈으로 Segmentation결과를 본 1015장을 Red,Green,Blue,Black으로 배경을 바꾼 4060장을
Fine-Tuning 시켜보았더니 전부 Accuracy가 떨어지는 현상이발생(1)

- 같은 hyperparmeter를 쓰더라도 어떨때는 낫고 어떨때는 떨어짐
  아마 어떤 사진을 먼저 학습하냐에 따라 조금씩 차이가 있는것으로 생각됨
- RRGB에 대한 acc는 90%가 넘는 경우도 있었으나 이 경우에도 TestSet에 대한 acc는 많이 떨어짐(2)
- RRGB를 적게쓸수록 TestSet에 대한 acc하락이 줄어드는 경향이 확인됨(3)

6.10
- Fine-Tuning이 아닌 백지의 ResNet에 Train(50000)+RRGB(1015*4)를 더해 섞은다음 처음부터 학습시켜봄(4)
  하지만 학습이 되지않고 Train(50000)만 가지고 fine-tuning하는 코드로 학습을 해도 학습이 되지않는 현상을 발견 (5)
  아마도 학습을 시키는 과정의 코드어딘가가 문제일수도
  ResNet백지에 내 코드와 수영님 코드(6)를 두개다 학습시켜본뒤 비교해보고 어떤게 문제인지 확인해보기
