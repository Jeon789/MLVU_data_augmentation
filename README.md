# MLVU_data_augmentation

# This is for fine-tuning of trained ResNet with CIFAR-10
- Data is augmented as changing background with RGB
- Keep in mind that batch_size = 100 is fixed through out this task
- So, the train set = 500 * 100 * 32 * 32 * 32 ( or 500 * 100 * 3 * 32 * 32) , test set = 100 * 100 * 32 * 32 * 3 ( or 100 * 100 * 3 * 32 * 32 )


[ Criterions ]

Fine-tuning    O      X

Thr           150   Human

Background    RGBB    7


-(1)Pre-trained ResNet에 28519*4로 fine- tuning한 결과 84.4%가 됨.

-(2)Pre-trained ResNet에 1015*4로 fine-tuning한 결과 81.5%가 됨

-(3) (1)에서 Fine-tuning data를 random으로 몇개만 뽑아서 해봄 84.4%와 거의 비슷

-(4-1) ResNet Train+RGBB(28519*4) 섞어서 처음부터 학습  86.5%

-(4-2) ResNet Train+RGBB(1015*4) 섞어서 처음부터 학습 88.77%

-(4-3) "(4-3) 수정완료본 이거대로 돌리면됨" 여기에 저장됨 이제 이걸로 (4-1),(4-2) ㄱㄱ


-(8-1) Only use well segmened data (1015)           1015개만으로 학습시켜봄

-(8-2) Only use well segmened data (1015 + 1015*4)  1015 + 1015*4 로 학습시켜봄

-(8-3) Only use well segmened data 1015 + 1015 ( original + Black )

-(8-5) FT - 0 . Thr = Human , Background - only black

-(8-6) Only use well segmented data (1015 + 1015*4) on Pre-trained ResNet


-(7) Backgound를 각 Class를 대표하는 배경 7개를 임의로 선택

-(7-8) 1015 + 1015*7 로 학습

-(7-1) FT-O , Thr =  150  , Background-7   80.69%

-(7-2) FT-O , Thr = Human , Background-7   76.33%

-(7-3) FT-X , Thr =  150  , Background-7   86.94%

-(7-4) FT-X , Thr = Human , Background-7   89.04%
