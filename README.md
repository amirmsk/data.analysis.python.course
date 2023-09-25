# data.analysis.python.course
free code camp
!pip install numpy
import numpy as np

def calculate(matrix):

  if len(matrix) != 9:
    raise ValueError("List must contain nine numbers.")

  # Convert the list to a 3 x 3 NumPy array.
  matrix = np.array(matrix).reshape((3, 3))

  # Calculate the mean, variance, standard deviation, max, min, and sum along both axes and for the flattened matrix.
  axis1_mean = np.mean(matrix, axis=0).round(2).tolist()
  axis2_mean = np.mean(matrix, axis=1).round(2).tolist()
  flattened_mean = np.mean(matrix.flatten()).round(2).tolist()

  axis1_variance = np.var(matrix, axis=0).round(2).tolist()
  axis2_variance = np.var(matrix, axis=1).round(2).tolist()
  flattened_variance = np.var(matrix.flatten()).round(2).tolist()

  axis1_std = np.std(matrix, axis=0).round(2).tolist()
  axis2_std = np.std(matrix, axis=1).round(2).tolist()
  flattened_std = np.std(matrix.flatten()).round(2).tolist()

  axis1_max = np.max(matrix, axis=0).round(2).tolist()
  axis2_max = np.max(matrix, axis=1).round(2).tolist()
  flattened_max = np.max(matrix.flatten()).round(2).tolist()

  axis1_min = np.min(matrix, axis=0).round(2).tolist()
  axis2_min = np.min(matrix, axis=1).round(2).tolist()
  flattened_min = np.min(matrix.flatten()).round(2).tolist()

  axis1_sum = np.sum(matrix, axis=0).round(2).tolist()
  axis2_sum = np.sum(matrix, axis=1).round(2).tolist()
  flattened_sum = np.sum(matrix.flatten()).round(2).tolist()


  return {
    "mean": [axis1_mean, axis2_mean, flattened_mean],
    "variance": [axis1_variance, axis2_variance, flattened_variance],
    "standard deviation": [axis1_std, axis2_std, flattened_std],
    "max": [axis1_max, axis2_max, flattened_max],
    "min": [axis1_min, axis2_min, flattened_min],
    "sum": [axis1_sum, axis2_sum, flattened_sum],
  }
