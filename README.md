# Deep Learning Figures

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)


These figures have been made mostly during [my PhD](https://www.thomas-robert.fr/en/resume/). Some present general concepts / models of Deep Learning, most are to describe the papers I worked on. The source is a [PPTX file containing all the figures](0_all_figures.pptx). You can try to adapt them to your needs if you feel up for it. If so, I recommend to install the [fonts](0_fonts) that I used.

These figures are used in [my PhD thesis](https://hal.archives-ouvertes.fr/tel-02309812) if you want to see them used in context and want a full legend.


**How I use PowerPoint figures in my LaTeX documents?**

For each paper, I have an `images/figures.pptx` file that contains all my PowerPoint figures. Regularly, I export this PowerPoint into a `images/figures.pdf` file. I also have a script `images/process_figures.sh` and run it after each PDF export:

```bash
# Split the PDF into pages
pdfsplit.py figures.pdf
# pdfsplit.py is included in this repo. It is designed for Mac. For Linux or Windows, you can find equivalents.

# Remove pages that I keep in the PPTX but I don't actually want to use
rm figures-3.pdf
rm figures-4.pdf

# Compress some pages if needed, when they contain big images, you need 
compress_pdf () {
    gs -sDEVICE=pdfwrite -dNOPAUSE -dQUIET -dBATCH -dPDFSETTINGS=/printer -dCompatibilityLevel=1.4 -sOutputFile=$1-comp.pdf $1.pdf
    mv $1-comp.pdf $1.pdf
}
compress_pdf figures-1 &
compress_pdf figures-2 &
wait

# Remove the write part of each figure's page
for f in `ls _deep-*.pdf`; do
    pdfcrop $f $f  &  # pdfcrop came with my latex install. It's this: https://ctan.org/pkg/pdfcrop
done
wait

# Rename into more usable names
mv figures-1.pdf intro_CV.pdf
mv figures-2.pdf intro_ML.pdf
# ...
```


## General figures

<p align="center">
	<strong>Intro of Computer Vision</strong>
</p>

<p align="center">
	<a href="1_01_intro_CV.png"><img src="1_01_intro_CV.png" width="450"></a><br>
	<a href="1_01_intro_CV.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Intro of Machine Learning</strong>
</p>

<p align="center">
	<a href="1_02_intro_ML.png"><img src="1_02_intro_ML.png" width="450"></a><br>
	<a href="1_02_intro_ML.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Intro of Neural Nets</strong>
</p>

<p align="center">
	<a href="1_03_neural_net.png"><img src="1_03_neural_net.png" width="450"></a><br>
	<a href="1_03_neural_net.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Intro of ConvNets</strong>
</p>

<p align="center">
	<a href="1_04_intro_CNN.png"><img src="1_04_intro_CNN.png" width="450"></a><br>
	<a href="1_04_intro_CNN.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Intro of Disentangling</strong>
</p>

<p align="center">
	<a href="1_05_intro_disentangling.png"><img src="1_05_intro_disentangling.png" width="450"></a><br>
	<a href="1_05_intro_disentangling.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Famous ConvNets architectures</strong>
</p>

<p align="center">
	<a href="1_06_intro_archis.png"><img src="1_06_intro_archis.png" width="450"></a><br>
	<a href="1_06_intro_archis.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>VGG architecture by [T. Durand](https://github.co</
	</durandtibo/deep_archi_latex)**

<p align="center">
	<a href="1_07_intro_VGG.png"><img src="1_07_intro_VGG.png" width="450"></a><br>
	<a href="1_07_intro_VGG.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</strong>

<p align="center">
	<strong>Illustration of Auto-Encoders</strong>
</durandtibo>

<p align="center">
	<a href="1_08_AE_auto_encoder.png"><img src="1_08_AE_auto_encoder.png" width="450"></a><br>
	<a href="1_08_AE_auto_encoder.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Illustration of Denoising Auto-Encoders</strong>
</p>

<p align="center">
	<a href="1_08_DAE_denosing_auto_encoder.png"><img src="1_08_DAE_denosing_auto_encoder.png" width="450"></a><br>
	<a href="1_08_DAE_denosing_auto_encoder.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Illustrations of Variational Auto-Encoders</strong>
</p>

<p align="center">
	<a href="1_09_VAE.png"><img src="1_09_VAE.png" width="450"></a><br>
	<a href="1_09_VAE.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<a href="1_10_VAE_variations.png"><img src="1_10_VAE_variations.png" width="450"></a><br>
	<a href="1_10_VAE_variations.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Illustration of GAN</strong>
</p>

<p align="center">
	<a href="1_11_GAN.png"><img src="1_11_GAN.png" width="450"></a><br>
	<a href="1_11_GAN.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Illustration of Ladder Networks</strong>
</p>

<p align="center">
	<a href="1_12_LadderNetworks.png"><img src="1_12_LadderNetworks.png" width="450"></a><br>
	<a href="1_12_LadderNetworks.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

## [SHADE: Information-Based Regularization for Deep Learning](https://arxiv.org/abs/1805.05814)


<p align="center">
	<strong>Goal of the model</strong>
</p>

<p align="center">
	<a href="2_01_shade_motivation.png"><img src="2_01_shade_motivation.png" width="450"></a><br>
	<a href="2_01_shade_motivation.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Minimizing Entropy</strong>
</p>

<p align="center">
	<a href="2_02_shade_entropy.png"><img src="2_02_shade_entropy.png" width="450"></a><br>
	<a href="2_02_shade_entropy.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Minimizing Conditional Entropy</strong>
</p>

<p align="center">
	<a href="2_03_shade_condentropy.png"><img src="2_03_shade_condentropy.png" width="450"></a><br>
	<a href="2_03_shade_condentropy.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

## [HybridNet: Classification and Reconstruction Cooperation for Semi-Supervised Learning](https://github.com/ThomasRobertFr/hybridnet)

<p align="center">
	<strong>Model overview</strong>
</p>

<p align="center">
	<a href="3_01_hybridnet_overview.png"><img src="3_01_hybridnet_overview.png" width="450"></a><br>
	<a href="3_01_hybridnet_overview.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Intuition</strong>
</p>

<p align="center">
	<a href="3_02_hybridnet_intuition.png"><img src="3_02_hybridnet_intuition.png" width="450"></a><br>
	<a href="3_02_hybridnet_intuition.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>General architecture</strong>
</p>

<p align="center">
	<a href="3_03_hybridnet_general-archi.png"><img src="3_03_hybridnet_general-archi.png" width="450"></a><br>
	<a href="3_03_hybridnet_general-pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Losses</strong>
</p>

<p align="center">
	<a href="3_04_hybridnet_losses.png"><img src="3_04_hybridnet_losses.png" width="450"></a><br>
	<a href="3_04_hybridnet_losses.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>ConvLarge architecture</strong>
</p>

<p align="center">
	<a href="3_05_hybridnet_convlarge.png"><img src="3_05_hybridnet_convlarge.png" width="450"></a><br>
	<a href="3_05_hybridnet_convlarge.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Example of architecture</strong>
</p>

<p align="center">
	<a href="3_06_hybridnet_archi_example.png"><img src="3_06_hybridnet_archi_example.png" width="450"></a><br>
	<a href="3_06_hybridnet_archi_example.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Branch balancing effect</strong>
</p>

<p align="center">
	<a href="3_07_hybridnet_balacing.png"><img src="3_07_hybridnet_balacing.png" width="450"></a><br>
	<a href="3_07_hybridnet_balacing.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Merge strategies</strong>
</p>

<p align="center">
	<a href="3_08_hybridnet_merge_early.png"><img src="3_08_hybridnet_merge_early.png" width="450"></a><br>
	<a href="3_08_hybridnet_merge_early.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<a href="3_09_hybridnet_merge_late.png"><img src="3_09_hybridnet_merge_late.png" width="450"></a><br>
	<a href="3_09_hybridnet_merge_late.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>HybridNet with SHADE</strong>
</p>

<p align="center">
	<a href="3_10_hybridnet_withshade.png"><img src="3_10_hybridnet_withshade.png" width="450"></a><br>
	<a href="3_10_hybridnet_withshade.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

## [DualDis: Dual-Branch Disentangling with Adversarial Learning](https://arxiv.org/abs/1906.00804)

<p align="center">
	<strong>Overview</strong>
</p>

<p align="center">
	<a href="4_01_dualdis_intro.png"><img src="4_01_dualdis_intro.png" width="450"></a><br>
	<a href="4_01_dualdis_intro.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Architecture</strong>
</p>

<p align="center">
	<a href="4_02_dualdis_archi.png"><img src="4_02_dualdis_archi.png" width="450"></a><br>
	<a href="4_02_dualdis_archi.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

<p align="center">
	<strong>Comparison with other models</strong>
</p>

<p align="center">
	<a href="4_03_dualdis_archis_details.png"><img src="4_03_dualdis_archis_details.png" width="450"></a><br>
	<a href="4_03_dualdis_archis_details.pdf"><img src="https://img.shields.io/badge/Download-PDF-blue"></a>
</p>

