
<div align="center">

  <h1>🔬 R Neurohacking Part 1</h1>

  <p>
    A neuroimaging workflow for processing, analyzing,
    and visualizing structural brain MRI data.
  </p>

</div>

<hr>

<h2>📑 Table of Contents</h2>

<ul>
  <li><a href="#objective">Objective</a></li>
  <li><a href="#project-details">Project Details</a></li>
  <li><a href="#r-scripts">R Scripts</a></li>
  <li><a href="#images">Images</a></li>
</ul>

<hr>

<h2 id="objective">🎯 Objective</h2>

<p>
  This project uses the R programming language and its
  neuroimaging packages to manipulate, process, and analyze
  structural brain MRI data in the NIfTI (Neuroimaging
  Informatics Technology Initiative) format. It focuses on
  performing inhomogeneity correction, brain extraction,
  image registration, and visualization to enable
  comprehensive exploration of neuroimaging data.
</p>

<hr>

<h2 id="project-details">🛠️ Project Details</h2>

<p>
  <strong>Tools:</strong> R
</p>

<hr>

<h2 id="r-scripts">🔵 R Scripts</h2>

<p>
  Each results folder contains the R Markdown script
  associated with that part of the neuroimaging workflow.
</p>

<h3>Parts 01–05</h3>

<p>
  <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_01/R_Neurohacking_Part_01.Rmd">View R Script 01</a>
  &nbsp; • &nbsp;
  <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_02/R_Neurohacking_Part_02.Rmd">View R Script 02</a>
  &nbsp; • &nbsp;
  <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_03/R_Neurohacking_Part_03.Rmd">View R Script 03</a>
  &nbsp; • &nbsp;
  <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_04/R_Neurohacking_Part_04.Rmd">View R Script 04</a>
  &nbsp; • &nbsp;
  <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_05/R_Neurohacking_Part_05.Rmd">View R Script 05</a>
</p>

<h3>Parts 06–10</h3>

<p>
  <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_06/R_Neurohacking_Part_06.Rmd">View R Script 06</a>
  &nbsp; • &nbsp;
  <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_07/R_Neurohacking_Part_07.Rmd">View R Script 07</a>
  &nbsp; • &nbsp;
  <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_08/R_Neurohacking_Part_08.Rmd">View R Script 08</a>
  &nbsp; • &nbsp;
  <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_09/R_Neurohacking_Part_09.Rmd">View R Script 09</a>
  &nbsp; • &nbsp;
  <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_10/R_Neurohacking_Part_10.Rmd">View R Script 10</a>
</p>

<h3>Parts 11–15</h3>

<p>
  <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_11/R_Neurohacking_Part_11.Rmd">View R Script 11</a>
  &nbsp; • &nbsp;
  <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_12/R_Neurohacking_Part_12.Rmd">View R Script 12</a>
  &nbsp; • &nbsp;
  <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_13/R_Neurohacking_Part_13.Rmd">View R Script 13</a>
  &nbsp; • &nbsp;
  <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_14/R_Neurohacking_Part_14.Rmd">View R Script 14</a>
  &nbsp; • &nbsp;
  <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_15/R_Neurohacking_Part_15.Rmd">View R Script 15</a>
</p>

<hr>

<h2 id="images">🖼️ Images</h2>

<p>
  Of the MRI slices numbered 1 to 22, slice 11 is shown
  as a representative example. Sample R code snippets
  demonstrate how the images were generated. Early slices
  were processed manually, while later stages used loops
  to make the workflow faster and more efficient.
</p>

<hr>

<h3>Part 01 — DICOM FLAIR</h3>

<h4>DICOM FLAIR Slice 11 Grayscale</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_01/DICOM_FLAIR_Slice_11_Grayscale.png">
        <img
          src="R_Neurohacking_Results_Part_01/DICOM_FLAIR_Slice_11_Grayscale.png"
          alt="DICOM FLAIR Slice 11 Grayscale"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#transpose data using t(): faces "up" versus "right", grayscale
d11 &lt;- dim(t(slice11$img[[1]]))
image(1:d11[1], 1:d11[2], t(slice11$img[[1]]), col = gray(0:64/64), main = "DICOM FLAIR Slice 11 Grayscale")

#subset img matrix (rows 101-105, columns 121-125)
slice11$img[[1]][101:105, 121:125] &lt;- matrix(c(
    4,   34,   36,   75,   222,
    9,   44,   33,   117,  248,
    19,  47,   54,   167,  274,
    27,  28,   98,   239,  286,
    12,  45,   170,  288,  307
), nrow = 5, byrow = TRUE)</code></pre>

</details>

<h4>DICOM FLAIR Slice 11 Histogram</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_01/DICOM_FLAIR_Slice_11_Histogram.png">
        <img
          src="R_Neurohacking_Results_Part_01/DICOM_FLAIR_Slice_11_Histogram.png"
          alt="DICOM FLAIR Slice 11 Histogram"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#create histogram in img
hist(slice11$img[[1]][,],
     breaks = 50,
     xlab = "FLAIR",
     prob = TRUE,
     col = rgb(0, 0, 1, 1/4),
     main = "DICOM FLAIR Slice 11 Histogram")</code></pre>

</details>

<hr>

<h3>Part 02 — DICOM T1</h3>

<h4>DICOM T1 Slice 11 Grayscale</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_02/DICOM_T1_Slice_11.png">
        <img
          src="R_Neurohacking_Results_Part_02/DICOM_T1_Slice_11.png"
          alt="DICOM T1 Slice 11 Grayscale"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#plot NIfT1 slice 11
image(1:d[1], 1:d[2], nii_T1[,,11],
  col = gray(0:64/64),
  xlab = "",
  ylab= "",
  main = "DICOM T1 Slice 11 Grayscale")</code></pre>

</details>

<hr>

<h3>Part 03 — DICOM T2</h3>

<h4>DICOM T2 Slice 11 Grayscale</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_03/DICOM_T2_Slice_11.png">
        <img
          src="R_Neurohacking_Results_Part_03/DICOM_T2_Slice_11.png"
          alt="DICOM T2 Slice 11 Grayscale"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#plot NIfT2 slice 11
image(1:d[1], 1:d[2], nii_T2[,,11],
  col = gray(0:64/64),
  xlab = "",
  ylab= "",
  main = "DICOM T2 Slice 11 Grayscale")</code></pre>

</details>

<hr>

<h3>Part 04 — NIfTI T1</h3>

<h4>NIfTI nii T1 Slice 11 Grayscale</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_04/NIfTI_nii_T1_Slice_11_Grayscale.png">
        <img
          src="R_Neurohacking_Results_Part_04/NIfTI_nii_T1_Slice_11_Grayscale.png"
          alt="NIfTI nii T1 Slice 11 Grayscale"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#read without reorientation
nii_T1 &lt;- readNIfTI(fname, reorient = FALSE)

#slice using custom x and y axes, grayscale, for slice 11
png("NIfTI_nii_T1_Slice_11_Grayscale.png", width = 800, height = 800)
image(1:d[1], 1:d[2], nii_T1[,,11], xlab = "", ylab = "", col = gray(0:64/64), main = "NIfTI nii T1 Slice 11 Grayscale")
dev.off()</code></pre>

</details>

<h4>NIfTI nii T1 Slice 11 Heat</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_04/NIfTI_nii_T1_Slice_11_Heat.png">
        <img
          src="R_Neurohacking_Results_Part_04/NIfTI_nii_T1_Slice_11_Heat.png"
          alt="NIfTI nii T1 Slice 11 Heat"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#read without reorientation
nii_T1 &lt;- readNIfTI(fname, reorient = FALSE)

#slice using custom x and y axes, default colors of heat color orange, for slice 11
png("NIfTI_nii_T1_Slice_11_Heat.png", width = 800, height = 800)
image(1:d[1], 1:d[2], nii_T1[,,11], xlab = "", ylab = "", col = heat.colors(12), main = "NIfTI nii T1 Slice 11 Heat")
dev.off()</code></pre>

</details>

<h4>NIfTI nii T1 Slice 11 Oro</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_04/NIfTI_nii_T1_Slice_11_Oro.png">
        <img
          src="R_Neurohacking_Results_Part_04/NIfTI_nii_T1_Slice_11_Oro.png"
          alt="NIfTI nii T1 Slice 11 Oro"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#read without reorientation
nii_T1 &lt;- readNIfTI(fname, reorient = FALSE)

#slice using oro.nifti package for slice 11
png("NIfTI_nii_T1_Slice_11_Oro.png", width = 800, height = 800)
image(nii_T1, z=11,plot.type="single")
mtext("NIfTI nii T1 Slice 11 Oro", side = 1, line = 1, adj = 1, cex = 1, col = "white")
dev.off()</code></pre>

</details>

<h4>NIfTI nii T1 Slice 11 Orthographic</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_04/NIfTI_nii_T1_Slice_11_Orthographic.png">
        <img
          src="R_Neurohacking_Results_Part_04/NIfTI_nii_T1_Slice_11_Orthographic.png"
          alt="NIfTI nii T1 Slice 11 Orthographic"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#read without reorientation
nii_T1 &lt;- readNIfTI(fname, reorient = FALSE)

#slice orthographic all planes of coronal, sagittal, and axial for slice 11, text
png("NIfTI_nii_T1_Slice_11_Orthographic.png", width = 800, height = 800)
orthographic(nii_T1, xyz = c(200, 220, 11))
mtext("NIfTI nii T1 Slice 11 Orthographic", side = 1, line = 1, adj = 1, cex = 1, col = "white")
dev.off()</code></pre>

</details>

<h4>NIfTI nii T1 Slice 11 Histogram</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_04/NIfTI_T1_Slice_11_Histogram.png">
        <img
          src="R_Neurohacking_Results_Part_04/NIfTI_T1_Slice_11_Histogram.png"
          alt="NIfTI nii T1 Slice 11 Histogram"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#plot area
par(mfrow=c(1,2))
o&lt;-par(mar=c(4,4,4,2))

#slice selection for slice 11
slice_data_11 &lt;- nii_T1[,,11]

#histogram with density and intensities for all in slice 11
hist(slice_data_11, breaks = 75, prob = TRUE, xlab = "T1 Intensities", col = rgb(0,0,1,0.5), main = "NIfTI nii T1 Slice 11 Histogram", cex.main = 1)

#histogram with density and intensities for &lt; 20 in slice 11
hist(slice_data_11[slice_data_11 &gt; 20], breaks = 75, prob = TRUE, xlab = "T1 Intensities &gt; 20", col = rgb(0,0,1,0.5), main = "NIfTI nii T1 Slice 11 Histogram (&gt;20)", cex.main = 1)

dev.off()</code></pre>

</details>

<hr>

<h3>Part 05 — NIfTI T2</h3>

<h4>NIfTI nii T2 Slice 11 Grayscale</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_05/NIfTI_nii_T2_Slice_11_Grayscale.png">
        <img
          src="R_Neurohacking_Results_Part_05/NIfTI_nii_T2_Slice_11_Grayscale.png"
          alt="NIfTI nii T2 Slice 11 Grayscale"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#read without reorientation
nii_T2 &lt;- readNIfTI(fname, reorient = FALSE)

#slice using custom x and y axes, grayscale, for slice 11
png("NIfTI_nii_T2_Slice_11_Grayscale.png", width = 800, height = 800)
image(1:d[1], 1:d[2], nii_T2[,,11], xlab = "", ylab = "", col = gray(0:64/64), main = "NIfTI nii T2 Slice 11 Grayscale")
dev.off()</code></pre>

</details>

<h4>NIfTI nii T2 Slice 11 Heat</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_05/NIfTI_nii_T2_Slice_11_Heat.png">
        <img
          src="R_Neurohacking_Results_Part_05/NIfTI_nii_T2_Slice_11_Heat.png"
          alt="NIfTI nii T2 Slice 11 Heat"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#read without reorientation
nii_T2 &lt;- readNIfTI(fname, reorient = FALSE)

#slice using custom x and y axes, default colors of heat color orange, for slice 11
png("NIfTI_nii_T2_Slice_11_Heat.png", width = 800, height = 800)
image(1:d[1], 1:d[2], nii_T2[,,11], xlab = "", ylab = "", col = heat.colors(12), main = "NIfTI nii T2 Slice 11 Heat")
dev.off()</code></pre>

</details>

<h4>NIfTI nii T2 Slice 11 Oro</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_05/NIfTI_nii_T2_Slice_11_Oro.png">
        <img
          src="R_Neurohacking_Results_Part_05/NIfTI_nii_T2_Slice_11_Oro.png"
          alt="NIfTI nii T2 Slice 11 Oro"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#read without reorientation
nii_T2 &lt;- readNIfTI(fname, reorient = FALSE)

#slice using oro.nifti package for slice 11
png("NIfTI_nii_T2_Slice_11_Oro.png", width = 800, height = 800)
image(nii_T2, z=11,plot.type="single")
mtext("NIfTI nii T2 Slice 11 Oro", side = 1, line = 1, adj = 1, cex = 1, col = "white")
dev.off()</code></pre>

</details>

<h4>NIfTI nii T2 Slice 11 Orthographic</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_05/NIfTI_nii_T2_Slice_11_Orthographic.png">
        <img
          src="R_Neurohacking_Results_Part_05/NIfTI_nii_T2_Slice_11_Orthographic.png"
          alt="NIfTI nii T2 Slice 11 Orthographic"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#read without reorientation
nii_T2 &lt;- readNIfTI(fname, reorient = FALSE)

#slice orthographic all planes of coronal, sagittal, and axial for slice 11, text
png("NIfTI_nii_T2_Slice_11_Orthographic.png", width = 800, height = 800)
orthographic(nii_T2, xyz = c(200, 220, 11))
mtext("NIfTI nii T2 Slice 11 Orthographic", side = 1, line = 1, adj = 1, cex = 1, col = "white")
dev.off()</code></pre>

</details>

<h4>NIfTI nii T2 Slice 11 Histogram</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_05/NIfTI_T2_Slice_11_Histogram.png">
        <img
          src="R_Neurohacking_Results_Part_05/NIfTI_T2_Slice_11_Histogram.png"
          alt="NIfTI nii T2 Slice 11 Histogram"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#read without reorientation
nii_T2 &lt;- readNIfTI(fname, reorient = FALSE)

#plot area
par(mfrow=c(1,2))
o&lt;-par(mar=c(4,4,4,2))

#slice selection for slice 11
slice_data_11 &lt;- nii_T2[,,11]

#histogram with density and intensities for all in slice 11
hist(slice_data_11, breaks = 75, prob = TRUE, xlab = "T2 Intensities", col = rgb(0,0,1,0.5), main = "NIfTI nii T2 Slice 11 Histogram", cex.main = 1)

#histogram with density and intensities for &lt; 20 in slice 11
hist(slice_data_11[slice_data_11 &gt; 20], breaks = 75, prob = TRUE, xlab = "T2 Intensities &gt; 20", col = rgb(0,0,1,0.5), main = "NIfTI nii T2 Slice 11 Histogram (&gt;20)", cex.main = 1)

dev.off()</code></pre>

</details>

<hr>

<h3>Part 06 — T1 Oro Overlays</h3>

<h4>NIfTI nii T1 Slice 11 Oro Overlay</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_06/NIfTI_nii_T1_Slice_11_Oro_Overlay.png">
        <img
          src="R_Neurohacking_Results_Part_06/NIfTI_nii_T1_Slice_11_Oro_Overlay.png"
          alt="NIfTI nii T1 Slice 11 Oro Overlay"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#define value between 300 and 400
is_btw_300_400 &lt;- (nii_T1 &gt;= 300) &amp; (nii_T1 &lt;= 400)

#mask
nii_T1_mask &lt;- nii_T1

#set value range to NA
nii_T1_mask[!is_btw_300_400] &lt;- NA

#extract the 3D data array
mask_array &lt;- nii_T1_mask[]

#slice 11
arr_11 &lt;- array(NA, dim = dim(as.array(nii_T1_mask)))
arr_11[,,11] &lt;- as.array(nii_T1_mask)[,,11]

nii_T1_mask_11 &lt;- nii_T1_mask
nii_T1_mask_11@.Data &lt;- arr_11

png("NIfTI_nii_T1_Slice_11_Oro_Overlay.png", width = 800, height = 800)
overlay(nii_T1, nii_T1_mask_11, z = 11, plot.type = "single")
mtext("NIfTI nii T1 Slice 11 Oro Overlay", side = 1, line = 1, adj = 1, cex = 1, col = "white")
dev.off()</code></pre>

</details>

<h4>NIfTI nii T1 Slices 01-22 Oro Overlay Grid</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_06/NIfTI_nii_T1_Slices_01_22_Oro_Overlay_Grid.png">
        <img
          src="R_Neurohacking_Results_Part_06/NIfTI_nii_T1_Slices_01_22_Oro_Overlay_Grid.png"
          alt="NIfTI nii T1 Slices 01-22 Oro Overlay Grid"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#slices 01-22
arr_all &lt;- array(NA, dim = dim(as.array(nii_T1_mask)))
arr_all[,,1:22] &lt;- as.array(nii_T1_mask)[,,1:22]

nii_T1_mask_all &lt;- nii_T1_mask
nii_T1_mask_all@.Data &lt;- arr_all

png("NIfTI_nii_T1_Slices_01_22_Oro_Overlay_Grid.png", width = 800, height = 800)
overlay(nii_T1, nii_T1_mask_all, z = 1:22, plot.type = "single")
mtext("NIfTI nii T1 Slices 01-22 Oro Overlay Grid", side = 1, line = 1, adj = 1, cex = 1, col = "white")
dev.off()</code></pre>

</details>

<hr>

<h3>Part 07 — T2 Oro Overlays</h3>

<h4>NIfTI nii T2 Slice 11 Oro Overlay</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_07/NIfTI_nii_T2_Slice_11_Oro_Overlay.png">
        <img
          src="R_Neurohacking_Results_Part_07/NIfTI_nii_T2_Slice_11_Oro_Overlay.png"
          alt="NIfTI nii T2 Slice 11 Oro Overlay"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#define value between 300 and 400
is_btw_300_400 &lt;- (nii_T2 &gt;= 300) &amp; (nii_T2 &lt;= 400)

#mask
nii_T2_mask &lt;- nii_T2

#set value range to NA
nii_T2_mask[!is_btw_300_400] &lt;- NA

#extract the 3D data array
mask_array &lt;- nii_T2_mask[]

#slice 11
arr_11 &lt;- array(NA, dim = dim(as.array(nii_T2_mask)))
arr_11[,,11] &lt;- as.array(nii_T2_mask)[,,11]

nii_T2_mask_11 &lt;- nii_T2_mask
nii_T2_mask_11@.Data &lt;- arr_11

png("NIfTI_nii_T2_Slice_11_Oro_Overlay.png", width = 800, height = 800)
overlay(nii_T2, nii_T2_mask_11, z = 11, plot.type = "single")
mtext("NIfTI nii T2 Slice 11 Oro Overlay", side = 1, line = 1, adj = 1, cex = 1, col = "white")
dev.off()</code></pre>

</details>

<h4>NIfTI nii T2 Slices 01-22 Oro Overlay Grid</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_07/NIfTI_nii_T2_Slices_01_22_Oro_Overlay_Grid.png">
        <img
          src="R_Neurohacking_Results_Part_07/NIfTI_nii_T2_Slices_01_22_Oro_Overlay_Grid.png"
          alt="NIfTI nii T2 Slices 01-22 Oro Overlay Grid"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#slices 01-22
arr_all &lt;- array(NA, dim = dim(as.array(nii_T2_mask)))
arr_all[,,1:22] &lt;- as.array(nii_T2_mask)[,,1:22]

nii_T2_mask_all &lt;- nii_T2_mask
nii_T2_mask_all@.Data &lt;- arr_all

png("NIfTI_nii_T2_Slices_01_22_Oro_Overlay_Grid.png", width = 800, height = 800)
overlay(nii_T2, nii_T2_mask_all, z = 1:22, plot.type = "single")
mtext("NIfTI nii T2 Slices 01-22 Oro Overlay Grid", side = 1, line = 1, adj = 1, cex = 1, col = "white")
dev.off()</code></pre>

</details>

<hr>

<h3>Part 08 — T1 Orthographic</h3>

<h4>NIfTI nii T1 Slice 11 Orthographic</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_08/NIfTI_nii_T1_Slice_11_Orthographic.png">
        <img
          src="R_Neurohacking_Results_Part_08/NIfTI_nii_T1_Slice_11_Orthographic.png"
          alt="NIfTI nii T1 Slice 11 Orthographic"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#read without reorientation
nii_T1 &lt;- readNIfTI(fname, reorient = FALSE)

#slice orthographic all planes of coronal, sagittal, and axial for slice 11, text
png("NIfTI_nii_T1_Slice_11_Orthographic.png", width = 800, height = 800)
orthographic(nii_T1, xyz = c(200, 220, 11))
mtext("NIfTI nii T1 Slice 11 Orthographic", side = 1, line = 1, adj = 1, cex = 1, col = "white")
dev.off()</code></pre>

</details>

<h4>NIfTI nii T1 Slice 11 Orthographic Overlay</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_08/NIfTI_nii_T1_Slice_11_Orthographic_Overlay.png">
        <img
          src="R_Neurohacking_Results_Part_08/NIfTI_nii_T1_Slice_11_Orthographic_Overlay.png"
          alt="NIfTI nii T1 Slice 11 Orthographic Overlay"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#define value between 300 and 400
is_btw_300_400 &lt;- (nii_T1 &gt;= 300) &amp; (nii_T1 &lt;= 400)

#mask
nii_T1_mask &lt;- nii_T1

#set value range to NA
nii_T1_mask[!is_btw_300_400] &lt;- NA

#extract the 3D data array
mask_array &lt;- nii_T1_mask[]

#mask for slice 11
mask_11_array &lt;- array(NA, dim = dim(mask_array))
mask_11_array[,,11] &lt;- mask_array[,,11]

#overlay for slice 11
overlay(nii_T1, nii_T1_mask, z = 11, plot.type = "single")

#overlay orthographic all planes of coronal, sagittal, and axial for slice 11
orthographic(nii_T1, nii_T1_mask, xyz = c(200, 220, 11))
mtext("NIfTI nii T1 Slice 11 Orthographic Overlay", side = 1, line = 1, adj = 1, cex = 1, col = "white")</code></pre>

</details>

<hr>

<h3>Part 09 — T2 Orthographic</h3>

<h4>NIfTI nii T2 Slice 11 Orthographic</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_09/NIfTI_nii_T2_Slice_11_Orthographic.png">
        <img
          src="R_Neurohacking_Results_Part_09/NIfTI_nii_T2_Slice_11_Orthographic.png"
          alt="NIfTI nii T2 Slice 11 Orthographic"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#read without reorientation
nii_T2 &lt;- readNIfTI(fname, reorient = FALSE)

#slice orthographic all planes of coronal, sagittal, and axial for slice 11
png("NIfTI_nii_T2_Slice_11_Orthographic.png", width = 800, height = 800)
orthographic(nii_T2, xyz = c(200, 220, 11))
mtext("NIfTI nii T2 Slice 11 Orthographic", side = 1, line = 1, adj = 1, cex = 1, col = "white")
dev.off()</code></pre>

</details>

<h4>NIfTI nii T2 Slice 11 Orthographic Overlay</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_09/NIfTI_nii_T2_Slice_11_Orthographic_Overlay.png">
        <img
          src="R_Neurohacking_Results_Part_09/NIfTI_nii_T2_Slice_11_Orthographic_Overlay.png"
          alt="NIfTI nii T2 Slice 11 Orthographic Overlay"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#define value between 300 and 400
is_btw_300_400 &lt;- (nii_T2 &gt;= 300) &amp; (nii_T2 &lt;= 400)

#mask
nii_T2_mask &lt;- nii_T2

#set value range to NA
nii_T2_mask[!is_btw_300_400] &lt;- NA

#extract the 3D data array
mask_array &lt;- nii_T2_mask[]

#mask for slice 11
mask_11_array &lt;- array(NA, dim = dim(mask_array))
mask_11_array[,,11] &lt;- mask_array[,,11]

#overlay for slice 11
overlay(nii_T2, nii_T2_mask, z = 11, plot.type = "single")

#overlay orthographic all planes of coronal, sagittal, and axial for slice 11
orthographic(nii_T2, nii_T2_mask, xyz = c(200, 220, 11))
mtext("NIfTI nii T2 Slice 11 Orthographic Overlay", side = 1, line = 1, adj = 1, cex = 1, col = "white")</code></pre>

</details>

<hr>

<h3>Part 10 — Kirby21 T1</h3>

<h4>Kirby21 T1 Orthographic Original</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_10/Kirby21_T1_Orthographic_Original.png">
        <img
          src="R_Neurohacking_Results_Part_10/Kirby21_T1_Orthographic_Original.png"
          alt="Kirby21 T1 Orthographic Original"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#view the orthographic
orthographic(T1)</code></pre>

</details>

<h4>Kirby21 T1 Orthographic Masked</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_10/Kirby21_T1_Orthographic_Masked.png">
        <img
          src="R_Neurohacking_Results_Part_10/Kirby21_T1_Orthographic_Masked.png"
          alt="Kirby21 T1 Orthographic Masked"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#view the binary mask
orthographic(mask)

#apply the mask to the original image
masked.T1 &lt;- T1 * mask
orthographic(masked.T1)</code></pre>

</details>

<h4>Kirby21 T1 Orthographic Subtract</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_10/Kirby21_T1_Orthographic_Subtract.png">
        <img
          src="R_Neurohacking_Results_Part_10/Kirby21_T1_Orthographic_Subtract.png"
          alt="Kirby21 T1 Orthographic Subtract"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#subtract baseline
subtract.T1 &lt;- T1.follow - T1

#calculate the min and max
min(subtract.T1)
max(subtract.T1)

#view the binary mask difference
orthographic(subtract.T1)</code></pre>

</details>

<hr>

<h3>Part 11 — T1 Histograms and Smoothing</h3>

<h4>NIfTI nii T1 Log-Scale Histogram</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_11/NIfTI_nii_T1_Log_Scale_Histogram.png">
        <img
          src="R_Neurohacking_Results_Part_11/NIfTI_nii_T1_Log_Scale_Histogram.png"
          alt="NIfTI nii T1 Log-Scale Histogram"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#convert to numeric values
T1_numeric &lt;- as.numeric(T1_img)

#key finite values
x &lt;- T1_numeric[is.finite(T1_numeric)]

#show number of valid voxels and first few values
print(length(x))
print(head(x))

#if no variation (all values same), jitter to avoid histogram issues
if (length(unique(x)) &lt; 2) x &lt;- jitter(x)

#compute histogram and replace zero counts with NA for log scaling
im_hist &lt;- hist(x, breaks = 20, plot = FALSE)
counts_log &lt;- ifelse(im_hist$counts &gt; 0, im_hist$counts, NA)

#plot a base plot on a log scale
par(mar = c(5, 4, 4, 4) + 0.3)
col1 &lt;- rgb(0, 0, 1, 0.5)
plot(im_hist$mids, counts_log, log = "y", type = "h", lwd = 10, lend = 2,
     col = col1, xlab = "Intensity Values", ylab = "Count (Log Scale)",
     main = "NIfTI nii T1 Log-Scale Histogram")

dev.off()</code></pre>

</details>

<h4>NIfTI nii T1 Log-Scale Histogram with Linear Transfer Function</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_11/NIfTI_nii_T1_Log_Scale_Histogram_Linear_Transfer_Function.png">
        <img
          src="R_Neurohacking_Results_Part_11/NIfTI_nii_T1_Log_Scale_Histogram_Linear_Transfer_Function.png"
          alt="NIfTI nii T1 Log-Scale Histogram with Linear Transfer Function"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#plot a base plot
plot(im_hist$mids, counts_log, log = "y", type = "h", lwd = 10, lend = 2,
     col = col1, xlab = "Intensity Values", ylab = "Count (Log Scale)",
     main = "NIfTI nii T1 Log-Scale Histogram with Linear Transfer Function")

#scaling factor
l &lt;- 1

#add the curve on the same plot
curve(x * l, from = min(im_hist$mids), to = max(im_hist$mids),
      col = "red", lwd = 3, add = TRUE)

#add secondary axis on right side to show original intensity scale
ticks &lt;- pretty(im_hist$mids)
max_val &lt;- max(x)
ticks_norm &lt;- ticks / max_val

axis(side = 4, at = ticks_norm, labels = ticks)

#add label for right axis
mtext("Original Intensity", side = 4, line = 2)

dev.off()</code></pre>

</details>

<h4>Log-Scale Histogram with Spline Transfer Function</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_11/NIfTI_nii_T1_Log_Scale_Histogram_Spline_Transfer_Function.png">
        <img
          src="R_Neurohacking_Results_Part_11/NIfTI_nii_T1_Log_Scale_Histogram_Spline_Transfer_Function.png"
          alt="Log-Scale Histogram with Spline Transfer Function"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#x as numeric intensity vector, im_hist as histogram object
max_x &lt;- max(x)

#plot a base plot
plot(im_hist$mids, counts_log, log = "y", type = "h", lwd = 10, lend = 2,
     col = rgb(0,0,1,0.5), xlab = "Intensity Values", ylab = "Count (Log Scale)",
     main = "NIfTI nii T1 Log-Scale Histogram with Spline Transfer Function")

#overlay the spline transfer function curve
curve(lin.sp(x, knots.vals * max_x, slp.vals),
      from = min(im_hist$mids), to = max(im_hist$mids),
      axes = FALSE, xlab = "", ylab = "", col = 2, lwd = 3, add = TRUE)

#add secondary axis on the right side
ticks &lt;- pretty(im_hist$mids)
ticks_norm &lt;- ticks / max_x
axis(side = 4, at = ticks_norm, labels = ticks)
mtext("Transformed Intensity", side = 4, line = 2)

#apply spline transfer to numeric data x
trans_T1 &lt;- lin.sp(x, knots.vals * max_x, slp.vals)</code></pre>

</details>

<h4>NIfTI nii T1 Slice 11 Original</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_11/NIfTI_nii_T1_Slice_11_Original.png">
        <img
          src="R_Neurohacking_Results_Part_11/NIfTI_nii_T1_Slice_11_Original.png"
          alt="NIfTI nii T1 Slice 11 Original"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<h4>NIfTI nii T1 Slice 11 Smoothed</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_11/NIfTI_nii_T1_Slice_11_Smoothed.png">
        <img
          src="R_Neurohacking_Results_Part_11/NIfTI_nii_T1_Slice_11_Smoothed.png"
          alt="NIfTI nii T1 Slice 11 Smoothed"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#smooth image with Gaussian smoother (~1 minute)
smooth.T1 &lt;- GaussSmoothArray(T1_img@.Data, voxdim = c(1,1,1),
                             ksize = 11, sigma = diag(3,3),
                             mask = NULL, var.norm = FALSE)

#convert back to nifti object
smooth_nifti &lt;- nifti(smooth.T1)

#visualize smoothed volume
orthographic(smooth_nifti)

num_slices &lt;- dim(T1_img@.Data)[3]

for(slice_index in 1:num_slices) {
  #extract original slice from raw image
  original_slice &lt;- T1_img@.Data[, , slice_index]

  #extract corresponding slice from smoothed data
  smoothed_slice &lt;- smooth_nifti@.Data[, , slice_index]</code></pre>

</details>

<h4>NIfTI nii T1 Slice 11 Transformed</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_11/NIfTI_nii_T1_Slice_11_Transformed.png">
        <img
          src="R_Neurohacking_Results_Part_11/NIfTI_nii_T1_Slice_11_Transformed.png"
          alt="NIfTI nii T1 Slice 11 Transformed"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#calculate start and end indices for transformed slice vector
  slice_size &lt;- nrow(original_slice) * ncol(original_slice)
  start_idx &lt;- (slice_index - 1) * slice_size + 1
  end_idx &lt;- slice_index * slice_size
  #extract transformed slice and reshape to matrix
  transformed_slice &lt;- matrix(trans_T1[start_idx:end_idx],
                              nrow = nrow(original_slice),
                              ncol = ncol(original_slice))</code></pre>

</details>

<hr>

<h3>Part 12 — T2 Histograms and Smoothing</h3>

<h4>NIfTI nii T2 Log-Scale Histogram</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_12/NIfTI_nii_T2_Log_Scale_Histogram.png">
        <img
          src="R_Neurohacking_Results_Part_12/NIfTI_nii_T2_Log_Scale_Histogram.png"
          alt="NIfTI nii T2 Log-Scale Histogram"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#convert to numeric values
T2_numeric &lt;- as.numeric(T2_img)

#key finite values
x &lt;- T2_numeric[is.finite(T2_numeric)]

#show number of valid voxels and first few values
print(length(x))
print(head(x))

#if no variation (all values same), jitter to avoid histogram issues
if (length(unique(x)) &lt; 2) x &lt;- jitter(x)

#compute histogram and replace zero counts with NA for log scaling
im_hist &lt;- hist(x, breaks = 20, plot = FALSE)
counts_log &lt;- ifelse(im_hist$counts &gt; 0, im_hist$counts, NA)

#plot a base plot on a log scale
par(mar = c(5, 4, 4, 4) + 0.3)
col1 &lt;- rgb(0, 0, 1, 0.5)
plot(im_hist$mids, counts_log, log = "y", type = "h", lwd = 10, lend = 2,
     col = col1, xlab = "Intensity Values", ylab = "Count (Log Scale)",
     main = "NIfTI nii T2 Log-Scale Histogram")

dev.off()</code></pre>

</details>

<h4>NIfTI nii T2 Log-Scale Histogram with Linear Transfer Function</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_12/NIfTI_nii_T2_Log_Scale_Histogram_Linear_Transfer_Function.png">
        <img
          src="R_Neurohacking_Results_Part_12/NIfTI_nii_T2_Log_Scale_Histogram_Linear_Transfer_Function.png"
          alt="NIfTI nii T2 Log-Scale Histogram with Linear Transfer Function"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#plot a base plot
plot(im_hist$mids, counts_log, log = "y", type = "h", lwd = 10, lend = 2,
     col = col1, xlab = "Intensity Values", ylab = "Count (Log Scale)",
     main = "NIfTI nii T2 Log-Scale Histogram with Linear Transfer Function")

#scaling factor
l &lt;- 1

#add the curve on the same plot
curve(x * l, from = min(im_hist$mids), to = max(im_hist$mids),
      col = "red", lwd = 3, add = TRUE)

#add secondary axis on right side to show original intensity scale
ticks &lt;- pretty(im_hist$mids)
max_val &lt;- max(x)
ticks_norm &lt;- ticks / max_val
axis(side = 4, at = ticks_norm, labels = ticks)

#add label for right axis
mtext("Original Intensity", side = 4, line = 2)

dev.off()</code></pre>

</details>

<h4>NIfTI nii T2 Log-Scale Histogram with Spline Transfer Function</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_12/NIfTI_nii_T2_Log_Scale_Histogram_Spline_Transfer_Function.png">
        <img
          src="R_Neurohacking_Results_Part_12/NIfTI_nii_T2_Log_Scale_Histogram_Spline_Transfer_Function.png"
          alt="NIfTI nii T2 Log-Scale Histogram with Spline Transfer Function"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#x as numeric intensity vector, im_hist as histogram object
max_x &lt;- max(x)

#plot a base plot
plot(im_hist$mids, counts_log, log = "y", type = "h", lwd = 10, lend = 2,
     col = rgb(0,0,1,0.5), xlab = "Intensity Values", ylab = "Count (Log Scale)",
     main = "NIfTI nii T2 Log-Scale Histogram with Spline Transfer Function")

#overlay the spline transfer function curve
curve(lin.sp(x, knots.vals * max_x, slp.vals),
      from = min(im_hist$mids), to = max(im_hist$mids),
      axes = FALSE, xlab = "", ylab = "", col = 2, lwd = 3, add = TRUE)

#add secondary axis on the right side
ticks &lt;- pretty(im_hist$mids)
ticks_norm &lt;- ticks / max_x
axis(side = 4, at = ticks_norm, labels = ticks)
mtext("Transformed Intensity", side = 4, line = 2)

#apply spline transfer to numeric data x
trans_T2 &lt;- lin.sp(x, knots.vals * max_x, slp.vals)</code></pre>

</details>

<h4>NIfTI nii T2 Slice 12 Original</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_12/NIfTI_nii_T2_Slice_11_Original.png">
        <img
          src="R_Neurohacking_Results_Part_12/NIfTI_nii_T2_Slice_11_Original.png"
          alt="NIfTI nii T2 Slice 12 Original"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<h4>NIfTI nii T2 Slice 12 Smoothed</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_12/NIfTI_nii_T2_Slice_11_Smoothed.png">
        <img
          src="R_Neurohacking_Results_Part_12/NIfTI_nii_T2_Slice_11_Smoothed.png"
          alt="NIfTI nii T2 Slice 12 Smoothed"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#smooth image with Gaussian smoother (~1 minute)
smooth.T2 &lt;- GaussSmoothArray(T2_img@.Data, voxdim = c(1,1,1),
                             ksize = 11, sigma = diag(3,3),
                             mask = NULL, var.norm = FALSE)

#convert back to nifti object
smooth_nifti &lt;- nifti(smooth.T2)

#visualize smoothed volume
orthographic(smooth_nifti)

num_slices &lt;- dim(T2_img@.Data)[3]

for(slice_index in 1:num_slices) {
  #extract original slice from raw image
  original_slice &lt;- T2_img@.Data[, , slice_index]

  #extract corresponding slice from smoothed data
  smoothed_slice &lt;- smooth_nifti@.Data[, , slice_index]</code></pre>

</details>

<h4>NIfTI nii T2 Slice 12 Transformed</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_12/NIfTI_nii_T2_Slice_11_Transformed.png">
        <img
          src="R_Neurohacking_Results_Part_12/NIfTI_nii_T2_Slice_11_Transformed.png"
          alt="NIfTI nii T2 Slice 12 Transformed"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#calculate start and end indices for transformed slice vector
  slice_size &lt;- nrow(original_slice) * ncol(original_slice)
  start_idx &lt;- (slice_index - 1) * slice_size + 1
  end_idx &lt;- slice_index * slice_size
  #extract transformed slice and reshape to matrix
  transformed_slice &lt;- matrix(trans_T2[start_idx:end_idx],
                              nrow = nrow(original_slice),
                              ncol = ncol(original_slice))</code></pre>

</details>

<hr>

<h3>Part 13 — FLAIR, T1, and T2 Slices</h3>

<h4>NIfTI nii Slice 11 FLAIR</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_13/NIfTI_nii_Slice_11_FLAIR.png">
        <img
          src="R_Neurohacking_Results_Part_13/NIfTI_nii_Slice_11_FLAIR.png"
          alt="NIfTI nii Slice 11 FLAIR"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#load FLAIR
mridir &lt;- "C:/Users/redef/OneDrive/Desktop/R_Neurohacking/R_Neurohacking_Data/BRAINIX/NIfTI"
sequence &lt;- "FLAIR"

#FLAIR
volume.f &lt;- readNIfTI(file.path(mridir, paste0(sequence, '.nii.gz')), reorient = FALSE)
volume.f &lt;- cal_img(volume.f)</code></pre>

</details>

<h4>NIfTI nii Slice 11 T1 Weighted</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_13/NIfTI_nii_Slice_11_T1_Weighted.png">
        <img
          src="R_Neurohacking_Results_Part_13/NIfTI_nii_Slice_11_T1_Weighted.png"
          alt="NIfTI nii Slice 11 T1 Weighted"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#load T1
sequence &lt;- "T1"
volume.t1 &lt;- readNIfTI(file.path(mridir, paste0(sequence, '.nii.gz')), reorient = FALSE)
volume.t1 &lt;- cal_img(volume.t1)

#T1-Weighted (T1)
sequence &lt;- "T1"
volume.t1 &lt;- readNIfTI(file.path(mridir, paste0(sequence, '.nii.gz')), reorient = FALSE)
volume.t1 &lt;- cal_img(volume.t1)</code></pre>

</details>

<h4>NIfTI nii Slice 11 T2 Weighted</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_13/NIfTI_nii_Slice_11_T2_Weighted.png">
        <img
          src="R_Neurohacking_Results_Part_13/NIfTI_nii_Slice_11_T2_Weighted.png"
          alt="NIfTI nii Slice 11 T2 Weighted"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#load T2
sequence &lt;- "T2"
volume.t2 &lt;- readNIfTI(file.path(mridir, paste0(sequence, '.nii.gz')), reorient = FALSE)
volume.t2 &lt;- cal_img(volume.t2)

#T2-Weighted (T2)
sequence &lt;- "T2"
volume.t2 &lt;- readNIfTI(file.path(mridir, paste0(sequence, '.nii.gz')), reorient = FALSE)
volume.t2 &lt;- cal_img(volume.t2)</code></pre>

</details>

<hr>

<h3>Part 14 — MPRAGE Comparisons</h3>

<h4>01 MPRAGE Mean</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_14/113-01-MPRAGE_Mean.png">
        <img
          src="R_Neurohacking_Results_Part_14/113-01-MPRAGE_Mean.png"
          alt="01 MPRAGE Mean"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#compute mean
mean_val_113_01_MPRAGE &lt;- mean(nim_113_01_MPRAGE)
mean_text_113_01_MPRAGE &lt;- paste0("113-01-MPRAGE.nii.gz Mean: ", round(mean_val_113_01_MPRAGE, 2))</code></pre>

</details>

<h4>02 MPRAGE Mean</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_14/113-02-MPRAGE_Mean.png">
        <img
          src="R_Neurohacking_Results_Part_14/113-02-MPRAGE_Mean.png"
          alt="02 MPRAGE Mean"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#compute mean
mean_val_113_02_MPRAGE &lt;- mean(nim_113_02_MPRAGE)
mean_text_113_02_MPRAGE &lt;- paste0("113-02-MPRAGE.nii.gz Mean: ", round(mean_val_113_02_MPRAGE, 2))</code></pre>

</details>

<h4>01 MPRAGE Difference</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_14/113-01-MPRAGE_Difference.png">
        <img
          src="R_Neurohacking_Results_Part_14/113-01-MPRAGE_Difference.png"
          alt="01 MPRAGE Difference"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#diverging color palettes
fcol1 &lt;- div_gradient_pal(low="blue", mid="yellow", high="red")
fcol2 &lt;- div_gradient_pal(low="blue", mid="yellow", high="red")

#113-01-MPRAGE difference image
sub_bias_113_01_MPRAGE &lt;- nim_113_01_MPRAGE - fast_img_113_01_MPRAGE
q1 &lt;- quantile(sub_bias_113_01_MPRAGE[sub_bias_113_01_MPRAGE != 0], probs = seq(0,1,by=0.1))</code></pre>

</details>

<h4>02 MPRAGE Difference</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_14/113-02-MPRAGE_Difference.png">
        <img
          src="R_Neurohacking_Results_Part_14/113-02-MPRAGE_Difference.png"
          alt="02 MPRAGE Difference"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#diverging color palettes
fcol1 &lt;- div_gradient_pal(low="blue", mid="yellow", high="red")
fcol2 &lt;- div_gradient_pal(low="blue", mid="yellow", high="red")

#113-02-MPRAGE difference image
sub_bias_113_02_MPRAGE &lt;- nim_113_02_MPRAGE - fast_img_113_02_MPRAGE
q2 &lt;- quantile(sub_bias_113_02_MPRAGE[sub_bias_113_02_MPRAGE != 0], probs = seq(0,1,by=0.1))</code></pre>

</details>

<h4>01 MPRAGE Histogram</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_14/113_01_MPRAGE_Slices_01_22_Histogram.png">
        <img
          src="R_Neurohacking_Results_Part_14/113_01_MPRAGE_Slices_01_22_Histogram.png"
          alt="01 MPRAGE Histogram"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#slices to plot
slices_01_22 &lt;- 1:22

#113-01-MPRAGE histogram slices 01-22
vals_113_01_MPRAGE &lt;- lapply(slices_01_22, function(x) {
  data.frame(
    Original = c(nim_113_01_MPRAGE[,,x]),
    BiasCorrected = c(fast_img_113_01_MPRAGE[,,x]),
    slice = x
  )
})
vals_113_01_MPRAGE &lt;- do.call(rbind, vals_113_01_MPRAGE)
v_113_01_MPRAGE &lt;- melt(vals_113_01_MPRAGE, id.vars="slice", variable.name="ImageType", value.name="Value")</code></pre>

</details>

<h4>02 MPRAGE Histogram</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_14/113_02_MPRAGE_Slices_01_22_Histogram.png">
        <img
          src="R_Neurohacking_Results_Part_14/113_02_MPRAGE_Slices_01_22_Histogram.png"
          alt="02 MPRAGE Histogram"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#slices to plot
slices_01_22 &lt;- 1:22

#113-02-MPRAGE histogram slices 01-22
vals_113_02_MPRAGE &lt;- lapply(slices_01_22, function(x) {
  data.frame(
    Original = c(nim_113_02_MPRAGE[,,x]),
    BiasCorrected = c(fast_img_113_02_MPRAGE[,,x]),
    slice = x
  )
})
vals_113_02_MPRAGE &lt;- do.call(rbind, vals_113_02_MPRAGE)
v_113_02_MPRAGE &lt;- melt(vals_113_02_MPRAGE, id.vars="slice", variable.name="ImageType", value.name="Value")</code></pre>

</details>

<hr>

<h3>Part 15 — MPRAGE Brain Extraction and Masks</h3>

<h4>01 MPRAGE Original</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_15/113_01_MPRAGE_Original.png">
        <img
          src="R_Neurohacking_Results_Part_15/113_01_MPRAGE_Original.png"
          alt="01 MPRAGE Original"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#file path for 113-01-MPRAGE.nii.gz
win_file_113_01_MPRAGE &lt;- "C:/R_Neurohacking_Data/kirby21/visit_1/113/113-01-MPRAGE.nii.gz"
wsl_file_113_01_MPRAGE &lt;- "/mnt/c/R_Neurohacking_Data/kirby21/visit_1/113/113-01-MPRAGE.nii.gz"

#read original 113-01-MPRAGE.nii.gz
nim_113_01_MPRAGE &lt;- readNIfTI(win_file_113_01_MPRAGE)</code></pre>

</details>

<h4>01 MPRAGE Binary Mask Overlay</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_15/113_01_MPRAGE_Binary_Mask_Overlay.png">
        <img
          src="R_Neurohacking_Results_Part_15/113_01_MPRAGE_Binary_Mask_Overlay.png"
          alt="01 MPRAGE Binary Mask Overlay"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#read extracted brain 113-01-MPRAGE.nii.gz
binary_mask_113_01_MPRAGE &lt;- readNIfTI(win_file_113_01_MPRAGE, reorient=FALSE)

#read original images 113-01-MPRAGE.nii.gz
fast_img_113_01_MPRAGE &lt;- readNIfTI(win_file_113_01_MPRAGE, reorient=FALSE)

#create masks 113-01-MPRAGE.nii.gz
binary_mask_overlay_113_01_MPRAGE &lt;- binary_mask_113_01_MPRAGE
binary_mask_overlay_113_01_MPRAGE[binary_mask_113_01_MPRAGE &lt;= 0] &lt;- NA</code></pre>

</details>

<h4>02 MPRAGE Original</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_15/113_02_MPRAGE_Original.png">
        <img
          src="R_Neurohacking_Results_Part_15/113_02_MPRAGE_Original.png"
          alt="02 MPRAGE Original"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#file path for 113-02-MPRAGE.nii.gz
win_file_113_02_MPRAGE &lt;- "C:/R_Neurohacking_Data/kirby21/visit_2/113/113-02-MPRAGE.nii.gz"
wsl_file_113_02_MPRAGE &lt;- "/mnt/c/R_Neurohacking_Data/kirby21/visit_2/113/113-02-MPRAGE.nii.gz"

#read original 113-02-MPRAGE.nii.gz
nim_113_02_MPRAGE &lt;- readNIfTI(win_file_113_02_MPRAGE)</code></pre>

</details>

<h4>02 MPRAGE Binary Mask Overlay</h4>

<table>
  <tr>
    <td>
      <a href="https://github.com/redefiningvicky/R-Neurohacking-Part-1/blob/main/R_Neurohacking_Results_Part_15/113_02_MPRAGE_Binary_Mask_Overlay.png">
        <img
          src="R_Neurohacking_Results_Part_15/113_02_MPRAGE_Binary_Mask_Overlay.png"
          alt="02 MPRAGE Binary Mask Overlay"
          width="100%"
        />
      </a>
    </td>
  </tr>
</table>

<details>
  <summary>View R Code Snippet</summary>

<pre><code>#read extracted brain 113-02-MPRAGE.nii.gz
binary_mask_113_02_MPRAGE &lt;- readNIfTI(win_file_113_02_MPRAGE, reorient=FALSE)

#read original images 113-02-MPRAGE.nii.gz
fast_img_113_02_MPRAGE &lt;- readNIfTI(win_file_113_02_MPRAGE, reorient=FALSE)

#create masks 113-02-MPRAGE.nii.gz
binary_mask_overlay_113_02_MPRAGE &lt;- binary_mask_113_02_MPRAGE
binary_mask_overlay_113_02_MPRAGE[binary_mask_113_02_MPRAGE &lt;= 0] &lt;- NA</code></pre>

</details>

<hr>

<div align="center">

  <p>
    <a href="https://github.com/redefiningvicky/Technical-Projects">
      Back to Technical Projects
    </a>
    &nbsp; • &nbsp;
    <a href="https://github.com/redefiningvicky/redefiningvicky">
      Back to Portfolio
    </a>
  </p>

</div>
