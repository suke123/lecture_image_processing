# 課題１レポート

亀の画像を原画像とする．この画像は縦244画像，横326画素によるディジタルカラー画像である．

ORG=imread('Lenna.png'); % 原画像の入力  
imagesc(ORG); axis image; % 画像の表示

によって，原画像を読み込み，表示した結果を図１に示す．

![原画像](https://github.com/suke123/lecture_image_processing/blob/master/%E8%AA%B2%E9%A1%8C%E6%8F%90%E5%87%BA/%E8%AA%B2%E9%A1%8C1/images/kame1-1.png)  
図1 原画像

原画像を1/2サンプリングするには，画像を1/2倍に縮小した後，2倍に拡大すればよい．なお，拡大する際には，単純補間するために「box」オプションを設定する．

IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大

1/2サンプリングの結果を図２に示す．

![原画像](https://github.com/suke123/lecture_image_processing/blob/master/%E8%AA%B2%E9%A1%8C%E6%8F%90%E5%87%BA/%E8%AA%B2%E9%A1%8C1/images/kame1-2.png)  
図2 1/2サンプリング

同様に原画像を1/4サンプリングするには，画像を1/2倍に縮小した後，2倍に拡大すればよい．すなわち，

IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大

とする．1/4サンプリングの結果を図３に示す．

![原画像](https://github.com/suke123/lecture_image_processing/blob/master/%E8%AA%B2%E9%A1%8C%E6%8F%90%E5%87%BA/%E8%AA%B2%E9%A1%8C1/images/kame1-4.png)  
図3 1/4サンプリング

1/8から1/64ンプリングは，

IMG = imresize(ORG,0.5); % 画像の縮小  
IMG2 = imresize(IMG,2,'box'); % 画像の拡大

を繰り返す．サンプリングの結果を図４～７に示す．

![原画像](https://github.com/suke123/lecture_image_processing/blob/master/%E8%AA%B2%E9%A1%8C%E6%8F%90%E5%87%BA/%E8%AA%B2%E9%A1%8C1/images/kame1-8.png)  
図4 1/8サンプリング

![原画像](https://github.com/suke123/lecture_image_processing/blob/master/%E8%AA%B2%E9%A1%8C%E6%8F%90%E5%87%BA/%E8%AA%B2%E9%A1%8C1/images/kame1-16.png)  
図5 1/16サンプリング

![原画像](https://github.com/suke123/lecture_image_processing/blob/master/%E8%AA%B2%E9%A1%8C%E6%8F%90%E5%87%BA/%E8%AA%B2%E9%A1%8C1/images/kame1-32.png)  
図6 1/32サンプリング

![原画像](https://github.com/suke123/lecture_image_processing/blob/master/%E8%AA%B2%E9%A1%8C%E6%8F%90%E5%87%BA/%E8%AA%B2%E9%A1%8C1/images/kame1-64.png)
図7 1/64サンプリング

このようにサンプリング幅が大きくなると，モザイク状のサンプリング歪みが発生する．
