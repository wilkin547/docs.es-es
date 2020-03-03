---
title: Recursos de entrenamiento de Azure sobre el generador de modelos
description: Una guía de recursos para Azure Machine Learning
ms.topic: reference
ms.date: 02/27/2020
ms.author: luquinta
author: luisquintanilla
ms.openlocfilehash: 866fd5a90d13f85f2f8a1aa45ff0e1efb0096642
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159304"
---
# <a name="model-builder-azure-training-resources"></a>Recursos de entrenamiento de Azure sobre el generador de modelos

A continuación le mostramos una guía para obtener más información sobre los recursos usados para entrenar modelos en Azure con el generador de modelos.

## <a name="what-is-an-azure-machine-learning-experiment"></a>¿Qué es un experimento de Azure Machine Learning?

Un experimento de Azure Machine Learning es un recurso que debe crearse antes de ejecutar el entrenamiento del generador de modelos en Azure.

El experimento encapsula la configuración y los resultados de una o más ejecuciones de entrenamiento de aprendizaje automático. Los experimentos pertenecen a un área de trabajo específica. La primera vez que se crea un experimento, su nombre se registra en el área de trabajo. Todas las ejecuciones posteriores: si se usa el mismo nombre de experimento, se registran como parte del mismo experimento. De lo contrario, se crea un nuevo experimento.

## <a name="what-is-an-azure-machine-learning-workspace"></a>¿Qué es un área de trabajo de Azure Machine Learning?

Un área de trabajo es un recurso de Azure Machine Learning que proporciona una ubicación central para todos los artefactos y recursos de Azure Machine Learning creados como parte de la ejecución de entrenamiento.

Para crear un área de trabajo de Azure Machine Learning, es necesario lo siguiente:

- Nombre: un nombre para el área de trabajo, de entre 3 y 33 caracteres. Los nombres solo pueden contener caracteres alfanuméricos y guiones. 
- Región: ubicación geográfica del centro de datos en el que se implementan el área de trabajo y los recursos. Se recomienda que elija una ubicación cercana a donde se encuentren usted o sus clientes.
- Grupo de recursos: un contenedor que aúna todos los recursos relacionados de una solución de Azure.

## <a name="what-is-an-azure-machine-learning-compute"></a>¿Qué es un proceso de Azure Machine Learning?

Un proceso de Azure Machine Learning es una máquina virtual Linux basada en la nube que se usa para el entrenamiento.

Para crear un área de trabajo de Azure Machine Learning, es necesario lo siguiente:

- Nombre: un nombre para el área de trabajo, de entre 2 y 16 caracteres. Los nombres solo pueden contener caracteres alfanuméricos y guiones.
- Tamaño de proceso

    El generador de modelos puede usar uno de los siguientes tipos de proceso optimizados para GPU:

    | Tamaño | vCPU | Memoria: GiB | GiB de almacenamiento temporal (SSD) | GPU | Memoria de GPU: GiB | Discos de datos máx. | Nº máx. NIC |
    |---|---|---|---|---|---|---|---|
    | Standard_NC12   | 12 | 112 | 680  | 2 | 24 | 48 | 2 |
    | Standard_NC24   | 24 | 224 | 1440 | 4 | 48 | 64 | 4 |

    Consulte la [documentación de máquinas virtuales Linux de la serie NC](https://docs.microsoft.com/azure/virtual-machines/nc-series?toc=/azure/virtual-machines/linux/toc.json&bc=/azure/virtual-machines/linux/breadcrumb/toc.json) para obtener más detalles sobre los tipos de proceso optimizados para GPU.

## <a name="training"></a>Aprendizaje

El entrenamiento en Azure solo está disponible para el escenario de clasificación de imágenes del generador de modelos. El algoritmo usado para entrenar estos modelos es una red neuronal profunda basada en la arquitectura ResNet50. El proceso de entrenamiento tarda algún tiempo, y la duración puede variar en función del tamaño del proceso seleccionado, así como de la cantidad de datos. La primera vez que se entrena un modelo, es probable que el tiempo de entrenamiento sea ligeramente mayor porque se deben aprovisionar los recursos. Puede realizar un seguimiento del progreso de las ejecuciones seleccionando el vínculo "Supervisar la ejecución actual en el portal de Azure" en Visual Studio.

## <a name="results"></a>Resultados

Una vez completado el entrenamiento, se agregan dos proyectos a la solución con los siguientes sufijos:

- *ConsoleApp*: aplicación de consola C# .NET Core que proporciona código de inicio para crear la canalización de predicción y realizar predicciones.
- *Model*: Una aplicación C# .NET Standard que contiene los modelos de datos que definen el esquema de datos del modelo de entrada y salida, así como los siguientes recursos:

  - bestModel.onnx: versión serializada del modelo en formato Open Neural Network Exchange (ONNX). ONNX es un formato de código abierto para modelos de IA que admite la interoperabilidad entre marcos como ML.NET, PyTorch y TensorFlow.
  - bestModelMap.json: lista de categorías utilizadas al crear predicciones para asignar la salida del modelo a una categoría de texto.
  - MLModel.zip: versión serializada de la canalización de predicción de ML.NET que usa la versión serializada del modelo *bestModel.onnx* para hacer predicciones y salidas de asignaciones mediante el archivo `bestModelMap.json`.

## <a name="use-the-machine-learning-model"></a>Uso del modelo de aprendizaje automático

Las clases `ModelInput` y `ModelOutput` del proyecto *Model* definen el esquema de entrada y salida esperadas del modelo, respectivamente.

En un escenario de clasificación de imágenes, `ModelInput` contiene dos columnas:

- `ImageSource`: ruta de acceso de la cadena de la ubicación de la imagen.
- `Label`: categoría a la que pertenece la imagen. `Label` solo se usa como entrada cuando se realiza el entrenamiento y no es necesario proporcionarlo al realizar predicciones.

`ModelOutput` contiene dos columnas:

- `Prediction`: categoría de predicción de la imagen.
- `Score`: lista de probabilidades para todas las categorías (la mayor pertenece a `Prediction`).

## <a name="troubleshooting"></a>Solución de problemas

### <a name="cannot-create-compute"></a>No se puede crear el proceso

Si se produce un error durante la creación de un proceso de Azure Machine Learning, el recurso de proceso puede seguir existiendo en un estado de error. Si intenta volver a crear el recurso de proceso con el mismo nombre, se produce un error en la operación. Para corregir este error, hay dos posibilidades:

- Crear un nuevo proceso con otro nombre
- Ir a Azure Portal y quitar el recurso de proceso original
