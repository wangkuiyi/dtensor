Since I left PyTorch Distributed team at Meta and joined Apple to work on Apple Foundation Models, I have been using AXLearn, which is built on top of JAX.

To help myself understand JAX's distributed arrays and how sharding across a device mesh could facilitate various parallelisms, I have been using `jax.debug.visualize_array_sharding` often.  In this [LinkedIn Post](https://www.linkedin.com/posts/yidewang_i-coauthored-this-notebook-with-wanchao-activity-7319523841595076608-bcm3?utm_source=share&utm_medium=member_desktop&rcm=ACoAAALdDjQBRj38KfRE5-nY27SqXVIIS8171vE) that I co-authored with Wanchao Liang, we show that visualizing the sharding is helpful.

It is glad to see my ex-team rolling out PyTorch's DTensor and proof its value by building FSDP2 and TorchTitan on top of it.  DTensor also has a sharding visualization, which calls `tabluate` to produce a humble visual effect.

This project shows that we could add a new visualization to DTensor's shardings, which looks like JAX's.

I changed the current sharding visualization code of DTensor and JAX's and make them work together.
