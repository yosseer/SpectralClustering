<h1 align ="center" ><strong>Spectral Clustering on Non-Convex Data</h1>
  <p align="center">
  <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png" width="100%" />
</p>
    <p><strong>Presented by:</strong> Yosser Fhal</p>
    <p>This project demonstrates <strong>Spectral Clustering</strong> for grouping non-convex datasets, such as circular or complex shapes. The notebook provides step-by-step explanations and visualizations.</p>

<div class="section">
        <h2>Why Spectral Clustering?</h2>
        <ul>
            <li>Traditional clustering (like K-Means) assumes convex (spherical) clusters and relies on distance.</li>
            <li>Spectral Clustering uses graph connectivity via eigenvalues/eigenvectors, making it ideal for non-convex shapes.</li>
            <li>Example: In social networks, community members may not be geographically close but are connected via relationships.</li>
        </ul>
    </div>

<div class="section">
        <h2>Project Overview</h2>
        <ul>
            <li>Manual implementation of Spectral Clustering without using sklearn's <code>SpectralClustering</code>.</li>
            <li>Comparison with K-Means on challenging non-convex datasets: noisy sine wave and concentric circles.</li>
            <li>Datasets are visualized before and after clustering.</li>
        </ul>
    </div>

<div class="section">
        <h2>Manual Spectral Clustering Steps</h2>
        <ol>
            <li>Build the affinity matrix using either k-nearest neighbors or RBF (Gaussian similarity).</li>
            <li>Compute the degree matrix <code>D</code> and Laplacian <code>L = D - A</code>.</li>
            <li>Find eigenvectors of the Laplacian.</li>
            <li>Normalize the eigenvectors row-wise.</li>
            <li>Cluster the eigenvectors using K-Means.</li>
        </ol>

  <pre><code>labels = manual_spectral_clustering(
    X, 
    n_clusters=2, 
    affinity='nearest_neighbors', 
    n_neighbors=15, 
    gamma=1.0
)</code></pre>
  </div>

 <div class="section">
        <h2>Sine Dataset</h2>
   <img width="1790" height="590" alt="Image" src="https://github.com/user-attachments/assets/e5407df6-b4e7-4f7b-9c8f-76707e1d7f70" />
        <p>Demonstrates clustering on a noisy sine wave, a non-convex shape:</p>
        <ul>
            <li>Raw sine dataset plotted in red.</li>
            <li>K-Means struggles due to non-convex shape.</li>
            <li>Manual Spectral Clustering successfully separates clusters based on graph connectivity.</li>
        </ul>
        <p>Silhouette Scores:</p>
        <ul>
            <li>K-Means: <code>sil_kmeans</code></li>
            <li>Manual Spectral Clustering: <code>sil_spectral</code></li>
        </ul>
    </div>

 <div class="section">
        <h2>Circle Dataset</h2>
   <img width="1790" height="590" alt="Image" src="https://github.com/user-attachments/assets/bbfaa6d4-2a0e-444b-9ec4-bad96c036b06" />
        <p>Clustering on concentric circles (non-convex clusters):</p>
        <ul>
            <li>Raw circles plotted in red.</li>
            <li>K-Means fails to separate inner and outer circles effectively.</li>
            <li>Manual Spectral Clustering with RBF affinity accurately separates all three clusters.</li>
        </ul>
        <p>Silhouette Scores:</p>
        <ul>
            <li>K-Means: <code>sil_kmeans_circles</code></li>
            <li>Manual Spectral Clustering: <code>sil_spectral_circles</code></li>
        </ul>
    </div>

  <div class="section">
    <h2>Visualizations</h2>
        <p>Plots include:</p>
        <ul>
            <li>Raw datasets (sine and circle)</li>
            <li>K-Means clustering results</li>
            <li>Manual Spectral Clustering results</li>
            <li>Interactive Plotly plots for exploration</li>
        </ul>
    </div>

   <div class="section">
        <h2>How to Run</h2>
        <ol>
            <li>Clone the repository.</li>
            <li>Open the Jupyter Notebook <code>Spectral_Clustering.ipynb</code>.</li>
            <li>Ensure dependencies are installed: <code>numpy, pandas, matplotlib, plotly, sklearn, scipy</code>.</li>
            <li>Run cells sequentially to reproduce the results and visualizations.</li>
        </ol>
    </div>

   <div class="section">
        <h2>Dependencies</h2>
        <ul>
            <li>Python 3.x</li>
            <li>numpy</li>
            <li>pandas</li>
            <li>matplotlib</li>
            <li>plotly</li>
            <li>scikit-learn</li>
            <li>scipy</li>
        </ul>
    </div>

   <div class="section">
        <h2>Author</h2>
        <p>Yosser Fhal</p>
    </div>
<p align="center">
  <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/colored.png" width="100%" />
</p>
