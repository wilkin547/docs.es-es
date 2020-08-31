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
# <a name="how-to-install-gpu-support-in-model-builder"></a><span data-ttu-id="5aa33-103">Procedimiento para instalar la compatibilidad con GPU en Model Builder</span><span class="sxs-lookup"><span data-stu-id="5aa33-103">How to install GPU support in Model Builder</span></span>

<span data-ttu-id="5aa33-104">Aprenda a instalar los controladores de GPU para usar la GPU con Model Builder.</span><span class="sxs-lookup"><span data-stu-id="5aa33-104">Learn how to install the GPU drivers to use your GPU with Model Builder.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="5aa33-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5aa33-105">Prerequisites</span></span>

- <span data-ttu-id="5aa33-106">Extensión de Visual Studio Model Builder</span><span class="sxs-lookup"><span data-stu-id="5aa33-106">Model Builder Visual Studio extension.</span></span> <span data-ttu-id="5aa33-107">La extensión se integra en Visual Studio a partir de la versión 16.6.1.</span><span class="sxs-lookup"><span data-stu-id="5aa33-107">The extension is built into Visual Studio as of version 16.6.1.</span></span>
- <span data-ttu-id="5aa33-108">[Extensión de compatibilidad con la GPU de Visual Studio Modern Builder](https://marketplace.visualstudio.com/items?itemName=MLNET.ModelBuilderGPU).</span><span class="sxs-lookup"><span data-stu-id="5aa33-108">[Model Builder Visual Studio GPU support extension](https://marketplace.visualstudio.com/items?itemName=MLNET.ModelBuilderGPU).</span></span>
- <span data-ttu-id="5aa33-109">Al menos una GPU compatible con CUDA.</span><span class="sxs-lookup"><span data-stu-id="5aa33-109">At least one CUDA compatible GPU.</span></span> <span data-ttu-id="5aa33-110">Para obtener una lista de las GPU compatibles, vea la [guía de NVIDIA](https://developer.nvidia.com/cuda-gpus).</span><span class="sxs-lookup"><span data-stu-id="5aa33-110">For a list of compatible GPUs, see [NVIDIA's guide](https://developer.nvidia.com/cuda-gpus).</span></span>
- <span data-ttu-id="5aa33-111">Cuenta de desarrollador de NVIDIA.</span><span class="sxs-lookup"><span data-stu-id="5aa33-111">NVIDIA developer account.</span></span> <span data-ttu-id="5aa33-112">En caso de no tener ninguna, [cree una cuenta gratuita](https://developer.nvidia.com/developer-program).</span><span class="sxs-lookup"><span data-stu-id="5aa33-112">If you don't have one, [create a free account](https://developer.nvidia.com/developer-program).</span></span>

## <a name="install-dependencies"></a><span data-ttu-id="5aa33-113">Instalar dependencias</span><span class="sxs-lookup"><span data-stu-id="5aa33-113">Install dependencies</span></span>

1. <span data-ttu-id="5aa33-114">Instale [CUDA v10.0](https://developer.nvidia.com/cuda-10.0-download-archive).</span><span class="sxs-lookup"><span data-stu-id="5aa33-114">Install [CUDA v10.0](https://developer.nvidia.com/cuda-10.0-download-archive).</span></span> <span data-ttu-id="5aa33-115">Asegúrese de instalar CUDA v10.0, y no cualquier otra versión más reciente.</span><span class="sxs-lookup"><span data-stu-id="5aa33-115">Make sure you install CUDA v10.0, not any other newer version.</span></span> <span data-ttu-id="5aa33-116">No puede tener varias versiones de CUDA instaladas.</span><span class="sxs-lookup"><span data-stu-id="5aa33-116">You cannot have multiple versions of CUDA installed.</span></span>
1. <span data-ttu-id="5aa33-117">Instale [cuDNN v7.6.4 para CUDA 10.0](https://developer.nvidia.com/rdp/cudnn-download).</span><span class="sxs-lookup"><span data-stu-id="5aa33-117">Install [cuDNN v7.6.4 for CUDA 10.0](https://developer.nvidia.com/rdp/cudnn-download).</span></span> <span data-ttu-id="5aa33-118">No puede tener varias versiones de cuDNN instaladas.</span><span class="sxs-lookup"><span data-stu-id="5aa33-118">You cannot have multiple versions of cuDNN installed.</span></span> <span data-ttu-id="5aa33-119">Después de descargar el archivo ZIP de cuDNN v7.6.4 y desempaquetarlo, copie `<CUDNN_zip_files_path>\cuda\bin\cudnn64_7.dll` en `<YOUR_DRIVE>\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin`.</span><span class="sxs-lookup"><span data-stu-id="5aa33-119">After downloading cuDNN v7.6.4 zip file and unpacking it, copy `<CUDNN_zip_files_path>\cuda\bin\cudnn64_7.dll` to `<YOUR_DRIVE>\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v10.0\bin`.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="5aa33-120">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="5aa33-120">Troubleshooting</span></span>

<span data-ttu-id="5aa33-121">**¿Cómo puedo saber qué GPU tengo?**</span><span class="sxs-lookup"><span data-stu-id="5aa33-121">**How do I know what GPU I have?**</span></span>

<span data-ttu-id="5aa33-122">Siga estas instrucciones:</span><span class="sxs-lookup"><span data-stu-id="5aa33-122">Follow instructions provided:</span></span>

1. <span data-ttu-id="5aa33-123">Haga clic con el botón derecho en el escritorio.</span><span class="sxs-lookup"><span data-stu-id="5aa33-123">Right-click on desktop</span></span>
1. <span data-ttu-id="5aa33-124">Si ve "Panel de control de NVIDIA" o "Pantalla de NVIDIA" en la ventana emergente, significa que tiene una GPU de NVIDIA.</span><span class="sxs-lookup"><span data-stu-id="5aa33-124">If you see "NVIDIA Control Panel" or "NVIDIA Display" in the pop-up window, you have an NVIDIA GPU</span></span>
1. <span data-ttu-id="5aa33-125">Haga clic en "Panel de control de NVIDIA" o en "Pantalla de NVIDIA" en la ventana emergente.</span><span class="sxs-lookup"><span data-stu-id="5aa33-125">Click on "NVIDIA Control Panel" or "NVIDIA Display" in the pop-up window</span></span>
1. <span data-ttu-id="5aa33-126">Consulte "Información de tarjeta gráfica".</span><span class="sxs-lookup"><span data-stu-id="5aa33-126">Look at "Graphics Card Information"</span></span>
1. <span data-ttu-id="5aa33-127">Verá el nombre de la GPU de NVIDIA.</span><span class="sxs-lookup"><span data-stu-id="5aa33-127">You will see the name of your NVIDIA GPU</span></span>

<span data-ttu-id="5aa33-128">**No veo el panel de control de NVIDIA (o no se abre), pero sé que tengo una GPU de NVIDIA.**</span><span class="sxs-lookup"><span data-stu-id="5aa33-128">**I don't see NVIDIA Control Panel (or it fails to open) but I know I have an NVIDIA GPU.**</span></span>

1. <span data-ttu-id="5aa33-129">Abra el Administrador de dispositivos</span><span class="sxs-lookup"><span data-stu-id="5aa33-129">Open Device Manager</span></span>
1. <span data-ttu-id="5aa33-130">Consulte los adaptadores de pantalla.</span><span class="sxs-lookup"><span data-stu-id="5aa33-130">Look at Display adapters</span></span>
1. <span data-ttu-id="5aa33-131">Instale el [controlador](https://www.nvidia.com/drivers) adecuado para la GPU.</span><span class="sxs-lookup"><span data-stu-id="5aa33-131">Install appropriate [driver](https://www.nvidia.com/drivers) for your GPU.</span></span>
