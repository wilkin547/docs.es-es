---
title: Procedimiento para instalar la compatibilidad con GPU en Model Builder
description: Descubra cómo instalar la compatibilidad con GPU en Model Builder
ms.date: 08/18/2020
author: luisquintanilla
ms.author: luquinta
ms.topic: how-to
ms.openlocfilehash: ce629efa4c12a69f87196de35ebfe4331dc0800f
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608557"
---
# <a name="how-to-install-gpu-support-in-model-builder"></a>Procedimiento para instalar la compatibilidad con GPU en Model Builder

Aprenda a instalar los controladores de GPU para usar la GPU con Model Builder.

## <a name="prerequisites"></a>Requisitos previos

- Extensión de Visual Studio Model Builder La extensión se integra en Visual Studio a partir de la versión 16.6.1.
- [Extensión de compatibilidad con la GPU de Visual Studio Modern Builder](https://marketplace.visualstudio.com/items?itemName=MLNET.ModelBuilderGPU).
- Al menos una GPU compatible con CUDA. Para obtener una lista de las GPU compatibles, vea la [guía de NVIDIA](https://developer.nvidia.com/cuda-gpus).
- Cuenta de desarrollador de NVIDIA. En caso de no tener ninguna, [cree una cuenta gratuita](https://developer.nvidia.com/developer-program).

## <a name="install-dependencies"></a>Instalar dependencias

1. Instale [CUDA v10.0](https://developer.nvidia.com/cuda-10.0-download-archive). Asegúrese de instalar CUDA v10.0, y no cualquier otra versión más reciente. No puede tener varias versiones de CUDA instaladas.
1. Instale [cuDNN v7.6.4 para CUDA 10.0](https://developer.nvidia.com/rdp/cudnn-download). No puede tener varias versiones de cuDNN instaladas. Después de descargar el archivo ZIP de cuDNN v7.6.4 y desempaquetarlo, copie `<CUDNN_zip_files_path>\cuda\bin\cudnn64_7.dll` en `<YOUR_DRIVE>\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin`.

## <a name="troubleshooting"></a>Solución de problemas

**¿Cómo puedo saber qué GPU tengo?**

Siga estas instrucciones:

1. Haga clic con el botón derecho en el escritorio.
1. Si ve "Panel de control de NVIDIA" o "Pantalla de NVIDIA" en la ventana emergente, significa que tiene una GPU de NVIDIA.
1. Haga clic en "Panel de control de NVIDIA" o en "Pantalla de NVIDIA" en la ventana emergente.
1. Consulte "Información de tarjeta gráfica".
1. Verá el nombre de la GPU de NVIDIA.

**No veo el panel de control de NVIDIA (o no se abre), pero sé que tengo una GPU de NVIDIA.**

1. Abra el Administrador de dispositivos
1. Consulte los adaptadores de pantalla.
1. Instale el [controlador](https://www.nvidia.com/drivers) adecuado para la GPU.
