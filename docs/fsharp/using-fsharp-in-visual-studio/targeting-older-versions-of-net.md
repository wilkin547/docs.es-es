---
title: "Elegir .NET Framework 2.0 en Windows 8 como versión de destino"
description: "Obtenga información acerca de la versión anterior de .NET Framework de destino cuando se usa F #."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 63989543-95c3-4ab7-81f3-3834a8b15010
ms.openlocfilehash: 2c0191267da5bee7b844c11cdee168ccfb3321c4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="targeting-older-versions-of-net"></a><span data-ttu-id="5f48c-104">Selección de destino para versiones anteriores de .NET</span><span class="sxs-lookup"><span data-stu-id="5f48c-104">Targeting Older Versions of .NET</span></span>

> [!NOTE]
<span data-ttu-id="5f48c-105">En este artículo no está actualizado con el más reciente de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5f48c-105">This article is not up to date with the latest Visual Studio.</span></span>  <span data-ttu-id="5f48c-106">Se va a actualizar.</span><span class="sxs-lookup"><span data-stu-id="5f48c-106">It will be updated.</span></span>

<span data-ttu-id="5f48c-107">El siguiente error puede aparecer si intentas tener como destino .NET Framework 2.0, 3.0 o 3.5 en F # del proyecto cuando se instala Visual Studio en Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="5f48c-107">The following error might appear if you try to target the .NET Framework 2.0, 3.0, or 3.5 in an F# project when Visual Studio is installed on Windows 8.1:</span></span> 

```
This project requires the 2.0 F# runtime, but that runtime is not installed.
```

<span data-ttu-id="5f48c-108">Este error se sabe que se producen en la combinación de las condiciones siguiente:</span><span class="sxs-lookup"><span data-stu-id="5f48c-108">This error is known to occur under the following combination of conditions:</span></span>


- <span data-ttu-id="5f48c-109">Ha instalado Visual Studio en Windows 8.1.</span><span class="sxs-lookup"><span data-stu-id="5f48c-109">You installed Visual Studio on Windows 8.1.</span></span>
<br />

- <span data-ttu-id="5f48c-110">No habilite .NET Framework 3.5 antes de instalar Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="5f48c-110">You didn’t enable the .NET Framework 3.5 before you installed Visual Studio.</span></span>
<br />

- <span data-ttu-id="5f48c-111">El proyecto tiene como destino .NET Framework 2.0, 3.0 o 3.5.</span><span class="sxs-lookup"><span data-stu-id="5f48c-111">Your project targets the .NET Framework 2.0, 3.0, or 3.5.</span></span>
<br />

<span data-ttu-id="5f48c-112">Cuando se instala Visual Studio, que detecta las versiones instaladas de .NET Framework e instala el Runtime de F # 2.0 sólo si .NET Framework 3.5 está instalado y habilitado.</span><span class="sxs-lookup"><span data-stu-id="5f48c-112">When you install Visual Studio, it detects the installed versions of the .NET Framework and installs the F# 2.0 Runtime only if the .NET Framework 3.5 is installed and enabled.</span></span>


## <a name="resolving-the-error"></a><span data-ttu-id="5f48c-113">Resolver el Error</span><span class="sxs-lookup"><span data-stu-id="5f48c-113">Resolving the Error</span></span>
<span data-ttu-id="5f48c-114">Para resolver este error, puede que ya sea una versión más reciente de .NET Framework de destino, o puede habilitar .NET Framework 3.5 en Windows 8.1 y, a continuación, instalar el runtime de F # 2.0 ejecutando el programa de instalación de Visual Studio con la **reparación** opción.</span><span class="sxs-lookup"><span data-stu-id="5f48c-114">To resolve this error, you can either target a newer version of the .NET Framework, or you can enable the .NET Framework 3.5 on Windows 8.1 and then install the F# 2.0 runtime by running the setup program for Visual Studio with the **Repair** option.</span></span>


#### <a name="to-enable-the-net-framework-35-on-windows-81"></a><span data-ttu-id="5f48c-115">Para habilitar .NET Framework 3.5 en Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="5f48c-115">To enable the .NET Framework 3.5 on Windows 8.1</span></span>

1. <span data-ttu-id="5f48c-116">En el **iniciar** pantalla, empieza a escribir **el Panel de Control**.</span><span class="sxs-lookup"><span data-stu-id="5f48c-116">On the **Start** screen, start to enter **Control Panel**.</span></span>
<br />  <span data-ttu-id="5f48c-117">A medida que escribe ese nombre, la **el Panel de Control** icono aparece bajo la **aplicaciones** encabezado.</span><span class="sxs-lookup"><span data-stu-id="5f48c-117">As you enter that name, the **Control Panel** icon appears under the **Apps** heading.</span></span>
<br />

2. <span data-ttu-id="5f48c-118">Elija la **el Panel de Control** icono, elija la **programas** icono y, a continuación, elija la **o desactivar las características de Windows Active** vínculo.</span><span class="sxs-lookup"><span data-stu-id="5f48c-118">Choose the **Control Panel** icon, choose the **Programs** icon, and then choose the **Turn Windows features on or off** link.</span></span>
<br />

3. <span data-ttu-id="5f48c-119">Asegúrese de que el **.NET Framework 3.5 (incluye .NET 2.0 y 3.0)** casilla de verificación está seleccionada y, a continuación, elija la **Aceptar** botón.</span><span class="sxs-lookup"><span data-stu-id="5f48c-119">Make sure that the **.NET Framework 3.5 (includes .NET 2.0 and 3.0)** check box is selected, and then choose the **OK** button.</span></span>
<br />  <span data-ttu-id="5f48c-120">No es necesario seleccionar las casillas de verificación para todos los nodos secundarios para los componentes opcionales de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5f48c-120">You don’t need to select the check boxes for any child nodes for optional components of the .NET Framework.</span></span>
<br />  <span data-ttu-id="5f48c-121">.NET Framework 3.5 está habilitada si no estaba inicializada.</span><span class="sxs-lookup"><span data-stu-id="5f48c-121">The .NET Framework 3.5 is enabled if it wasn't already.</span></span>
<br />


#### <a name="to-install-the-f-20-runtime"></a><span data-ttu-id="5f48c-122">Para instalar el runtime de F # 2.0</span><span class="sxs-lookup"><span data-stu-id="5f48c-122">To install the F# 2.0 runtime</span></span>

1. <span data-ttu-id="5f48c-123">En el Panel de Control, elija la **programas** vincular y, a continuación, elija la **programas y características** vínculo.</span><span class="sxs-lookup"><span data-stu-id="5f48c-123">In the Control Panel, choose the **Programs** link, and then choose the **Programs and Features** link.</span></span>
<br />

2. <span data-ttu-id="5f48c-124">En la lista de programas instalados, elija la edición de Visual Studio que ha instalado y, a continuación, elija la **cambio** botón.</span><span class="sxs-lookup"><span data-stu-id="5f48c-124">In the list of installed programs, choose the edition of Visual Studio that you installed, and then choose the **Change** button.</span></span>
<br />

3. <span data-ttu-id="5f48c-125">Cuando se inicia el programa de instalación, elija la **reparación** botón.</span><span class="sxs-lookup"><span data-stu-id="5f48c-125">After setup starts, choose the **Repair** button.</span></span>
<br />  <span data-ttu-id="5f48c-126">Para obtener más información, consulte [instalar Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).</span><span class="sxs-lookup"><span data-stu-id="5f48c-126">For more information, see [Installing Visual Studio](https://msdn.microsoft.com/library/e2h7fzkw.aspx).</span></span>
<br />
## <a name="see-also"></a><span data-ttu-id="5f48c-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f48c-127">See Also</span></span>
[<span data-ttu-id="5f48c-128">Visual F#</span><span class="sxs-lookup"><span data-stu-id="5f48c-128">Visual F#</span></span>](../index.md)
