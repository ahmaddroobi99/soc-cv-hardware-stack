# Interview question bank

Aimed at a ~3 year computer-vision software + hardware engineer.

## Warm-up

1. Name every block a 12 MP RAW frame touches before it becomes a JPEG.
2. Why is a 12 MP RAW12 frame (~18-24 MB) never stored in L2?
3. What is an MSHR and what happens when the file is full?
4. Convert 64 KiB and 4 MiB to bytes. Why do ARM manuals use KiB?
5. MIPI vs USB vs Ethernet as a camera pipe. When do you pick each?

## SoC architecture

6. Data path vs control path vs address path. Give one CV example of each.
7. Why does an SoC have both a coherent fabric and a non-coherent NoC?
8. How does NoC QoS stop camera DMA from starving the CPU?
9. big.LITTLE plus DVFS versus one fat core for an always-on vision duty cycle.
10. Why did 865 ship a discrete X55 modem while 808 integrated X10 LTE?

## Imaging and perception

11. Why run an ISP before an NPU for detection? When would you train and run on RAW?
12. Zero-copy path: ION / dma-buf / Gralloc / CVPixelBuffer between ISP, GPU, NPU.
13. Color spaces: Bayer, RGB, YUV 4:2:0, RGB planar for NN. Who converts, and where?
14. 30 fps preview + detector latency budget. Which block usually dominates?
15. How do you keep LiDAR + RGB + IMU timestamps aligned into a Kafka topic?

## CPU / GPU / memory

16. MSHR vs ROB vs store buffer. Three different in-flight structures.
17. Why a 4-way decode frontend still needs a 120-entry issue window.
18. Adreno vs Apple GPU vs a CUDA SM. What is portable in Vulkan / Metal / OpenCL?
19. What breaks if MSHRs exhaust during bursty ISP writeback?
20. Pointer authentication on A12 in one sentence.

## Wireless and cloud

21. Walk bits from a JPEG in DRAM onto a 5 GHz Wi-Fi carrier.
22. Why Kafka is a poor raw-video transport and a good metadata transport.
23. Glass-to-glass 80 ms budget: where do you spend the 80 ms?
24. Secure Enclave vs TrustZone vs GPU memory for FaceID embeddings.
25. How would you debug a MIPI CSI-2 link that trains in LP mode but drops HS packets?

## Model answers live in the README case study and CPU sections.
