# pytorch_fcn
pytorch implementation for FCN (VGG, ResNet)
bilinear interpulation in not working in my system can you please help me ? i face this error

RuntimeError                              Traceback (most recent call last)
<ipython-input-21-2f7d87ec6710> in <module>()
----> 1 net = SegResNet(num_classes, pretrained_net)

/media/hfahad/a7382dc9-2057-4d75-a274-f10dded99b19/OBJECT RECOGNATION/project/pytorch_fcn/model.py in __init__(self, num_classes, pretrained_net)
     54     self.pretrained_net = pretrained_net
     55     self.relu = nn.ReLU(inplace=True)
---> 56     self.conv5 = conv(512,256, stride=2, transposed=True)
     57     self.bn5 = bn(256)
     58     self.conv6 = conv(256,128, stride=2, transposed=True)

/media/hfahad/a7382dc9-2057-4d75-a274-f10dded99b19/OBJECT RECOGNATION/project/pytorch_fcn/model.py in conv(in_planes, out_planes, kernel_size, stride, dilation, bias, transposed)
     15       for x in range(kernel_size):
     16         w[y, x] = (1 - abs((x - centre) / stride)) * (1 - abs((y - centre) / stride))
---> 17     layer.weight.data.copy_(w.div(in_planes).repeat(out_planes, in_planes, 1, 1))
     18   else:
     19     padding = (kernel_size + 2 * (dilation - 1)) // 2

RuntimeError: The expanded size of the tensor (256) must match the existing size (512) at non-singleton dimension 1
