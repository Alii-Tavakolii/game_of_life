'''
Game of Life simulator
'''

import numpy as np
import random as rnd
import time
from matplotlib import pyplot as plt
from IPython.display import clear_output
height = 20

def next_day(uni):
  def adjacents(x, y):
    ans = 0
    for i in range(x - 1, x + 2):
      for j in range(y - 1, y + 2):
        if (i == x and j == y):
          continue
        if (uni[i % height][j % height] == 1):
          ans += 1
          # if(x == 1 and y == 1):
          #   print(i, j, uni[i][j])
    return ans
  # print(adjacents(1, 1))
  uni2 = np.zeros((height, height))
  for i in range(0, height):
    for j in range(0, height):
      if uni[i][j] == 1 and (adjacents(i, j) == 2 or adjacents(i, j) == 3):
        uni2[i][j] = 1
      elif uni[i][j] == 0 and adjacents(i, j) == 3:
        uni2[i][j] = 1
  return uni2

universe = np.zeros((height, height))

for i in range(0, 100):
  universe[rnd.randint(0, height - 1)][rnd.randint(0, height - 1)] = 1


for i in range(1000):
  # plt.figure()
  plt.imshow(universe)
  plt.show()
  clear_output(wait=True)
  universe = next_day(universe)
# print("finished")
