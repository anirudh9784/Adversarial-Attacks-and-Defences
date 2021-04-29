# Major Project

<h3> Title : An integrated Auto Encoder-Block Switching defense approach to prevent adversarial attacks </h3>
<p align="justify"> According to the recent studies, the vulnerability of state of the art Neural Networks to adversarial input samples has increased drastically. Neural network is an intermediate path or technique by which a computer learns to perform tasks using Machine learning algorithms. Machine Learning and Artificial Intelligence model has become fundamental aspect of life, such as self-driving cars, smart home devices, so any vulnerability is a significant concern. The smallest input deviations can fool these extremely literal systems and deceive their users as well as administrator into precarious situations. This article proposes a defense algorithm which utilizes the combination of an auto-encoder and block-switching architecture. Auto-coder is intended to remove any perturbations found in input images whereas block switching method is used to make it more robust against White-box attack. Attack is planned using FGSM model, and the subsequent counter-attack by the proposed architecture will take place thereby demonstrating the feasibility and security delivered by the algorithm.</p>

<!DOCTYPE html>
<?php
    $dir = 'Dataset';
    $files = scandir($dir);
    $ext = '.png';
    foreach ($files as $img) {
        if ( substr_compare($img, $ext, -strlen($ext), strlen($ext)) === 0 ) {
           
                <h2 style="font-family: monospace;"><?=$img?></h2>
                <div style="text-align: center; margin-bottom: 100px;">
                    <img src="img/<?=$img?>">
                </div>
            
        }
    }
?>
</html>
