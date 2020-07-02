---
title: Cómo agregar una pantalla de presentación
description: Obtenga información sobre cómo agregar una ventana de inicio o una pantalla de presentación a una aplicación Windows Presentation Foundation (WPF).
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 0d0cf2e2a550320650c3b4a0c257071a0403c32b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617965"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="f9597-103">Cómo: Agregar una pantalla de presentación a una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="f9597-103">How to: Add a Splash Screen to a WPF Application</span></span>

<span data-ttu-id="f9597-104">En este tema se muestra cómo agregar una ventana de inicio o una *pantalla de presentación*a una aplicación Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="f9597-104">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>

## <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="f9597-105">Para agregar una imagen existente como pantalla de presentación</span><span class="sxs-lookup"><span data-stu-id="f9597-105">To add an existing image as a splash screen</span></span>

1. <span data-ttu-id="f9597-106">Cree o busque una imagen que desee usar para la pantalla de presentación.</span><span class="sxs-lookup"><span data-stu-id="f9597-106">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="f9597-107">Puede usar cualquier formato de imagen que sea compatible con el componente de creación de imágenes de Windows (WIC).</span><span class="sxs-lookup"><span data-stu-id="f9597-107">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="f9597-108">Por ejemplo, puede usar el formato BMP, GIF, JPEG, PNG o TIFF.</span><span class="sxs-lookup"><span data-stu-id="f9597-108">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>

2. <span data-ttu-id="f9597-109">Agregue el archivo de imagen al proyecto de aplicación de WPF.</span><span class="sxs-lookup"><span data-stu-id="f9597-109">Add the image file to the WPF Application project.</span></span>

3. <span data-ttu-id="f9597-110">En **Explorador de soluciones**, seleccione la imagen.</span><span class="sxs-lookup"><span data-stu-id="f9597-110">In **Solution Explorer**, select the image.</span></span>

4. <span data-ttu-id="f9597-111">En el ventana Propiedades, haga clic en la flecha desplegable de la propiedad **acción de compilación** .</span><span class="sxs-lookup"><span data-stu-id="f9597-111">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>

5. <span data-ttu-id="f9597-112">Seleccione **SplashScreen** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="f9597-112">Select **SplashScreen** from the drop-down list.</span></span>

6. <span data-ttu-id="f9597-113">Presione **F5** para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f9597-113">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="f9597-114">La imagen de la pantalla de presentación aparece en el centro de la pantalla y, a continuación, se atenúa cuando aparece la ventana de la aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="f9597-114">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>

## <a name="to-exclude-the-splash-screen-from-build"></a><span data-ttu-id="f9597-115">Para excluir la pantalla de presentación de la compilación</span><span class="sxs-lookup"><span data-stu-id="f9597-115">To exclude the splash screen from build</span></span>

1. <span data-ttu-id="f9597-116">En **Explorador de soluciones**, seleccione la imagen de la pantalla de presentación.</span><span class="sxs-lookup"><span data-stu-id="f9597-116">In **Solution Explorer**, select the splash screen image.</span></span>

2. <span data-ttu-id="f9597-117">En la ventana **propiedades** , establezca la **acción de compilación** en **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="f9597-117">In the **Properties** window, set the **Build Action** to **None**.</span></span>

## <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="f9597-118">Para quitar la pantalla de presentación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="f9597-118">To remove the splash screen from an application</span></span>

<span data-ttu-id="f9597-119">En **Explorador de soluciones**, elimine la imagen de la pantalla de presentación.</span><span class="sxs-lookup"><span data-stu-id="f9597-119">In **Solution Explorer**, delete the splash screen image.</span></span>

## <a name="see-also"></a><span data-ttu-id="f9597-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9597-120">See also</span></span>

- <xref:System.Windows.SplashScreen>
- <span data-ttu-id="f9597-121">[Cómo agregar elementos existentes a un proyecto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="f9597-121">[How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span></span>
