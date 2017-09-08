## How SVMs Project Into Higher Dimensions

I've always understood that in order to find decision boundaries for data that isn't linearly separable, SVMs project the data into a higher dimension where the data does become linearly separable with a hyperplane. However, I never understood how they find the _right_ projection.

It turns out that to find a decision boundary, the SVM only needs the **dot products** of each pair of points. It also turns out that rather than projecting the data into a higher dimension first and then computing the dot product, it's far more efficient to compute the dot product in projected space _by using the points in the original space as input_. This is exactly what the kernel function does. This [Stats and Bots blog post](https://blog.statsbot.co/support-vector-machines-tutorial-c1618e635e93) has a fantastic breakdown comparing projection into higher dimensions vs. how the kernel function achieves the same result.

While it is possible to write your own kernel (this could be thought of as injecting domain knowledge into the problem), most SVM libraries come with popular kernels that work well on many datasets. The Radial Basis Function (RBF) kernel is particularly interesting because it effectively projects the data into infinite-dimensional space.

The following summary is taken directly from the previously mentioned blog post:
1. We typically don’t define a specific projection for our data. Instead, we pick from available kernels, tweaking them in some cases, to find one best suited to the data.
2. Of course, nothing stops us from defining our own kernels, or performing the projection ourselves, but in many cases we don’t need to. Or we at least start by trying out what’s already available.
3. If there is a kernel available for the projection we want, we prefer to use the kernel, because that’s often faster.
4. RBF kernels can project points to infinite dimensions.