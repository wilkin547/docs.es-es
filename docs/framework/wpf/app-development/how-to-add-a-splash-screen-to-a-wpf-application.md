---
title: 'Cómo: Agregar una pantalla de presentación a una aplicación WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 06d6cb7c5a5081d3b6c4979ab50e1caaa726acbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33547006"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="cc585-102">Cómo: Agregar una pantalla de presentación a una aplicación WPF</span><span class="sxs-lookup"><span data-stu-id="cc585-102">How to: Add a Splash Screen to a WPF Application</span></span>
<span data-ttu-id="cc585-103">Este tema muestra cómo agregar una ventana de inicio, o *pantalla de presentación*, a una aplicación de Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="cc585-103">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>  
  
### <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="cc585-104">Para agregar una imagen existente como una pantalla de presentación</span><span class="sxs-lookup"><span data-stu-id="cc585-104">To add an existing image as a splash screen</span></span>  
  
1.  <span data-ttu-id="cc585-105">Cree o busque una imagen que se va a utilizar para la pantalla de presentación.</span><span class="sxs-lookup"><span data-stu-id="cc585-105">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="cc585-106">Puede utilizar cualquier formato de imagen que sea compatible con Windows Imaging Component (WIC).</span><span class="sxs-lookup"><span data-stu-id="cc585-106">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="cc585-107">Por ejemplo, puede usar el formato BMP, GIF, JPEG, PNG o TIFF.</span><span class="sxs-lookup"><span data-stu-id="cc585-107">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>  
  
2.  <span data-ttu-id="cc585-108">Agregue el archivo de imagen al proyecto de aplicación de WPF.</span><span class="sxs-lookup"><span data-stu-id="cc585-108">Add the image file to the WPF Application project.</span></span> <span data-ttu-id="cc585-109">Para obtener más información, consulte [NIB: Cómo: agregar elementos existentes a un proyecto](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span><span class="sxs-lookup"><span data-stu-id="cc585-109">For more information, see [NIB:How to: Add Existing Items to a Project](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3).</span></span>  
  
3.  <span data-ttu-id="cc585-110">En el Explorador de soluciones, seleccione la imagen.</span><span class="sxs-lookup"><span data-stu-id="cc585-110">In Solution Explorer, select the image.</span></span>  
  
4.  <span data-ttu-id="cc585-111">En la ventana Propiedades, haga clic en la flecha de lista desplegable para la **acción de compilación** propiedad.</span><span class="sxs-lookup"><span data-stu-id="cc585-111">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>  
  
5.  <span data-ttu-id="cc585-112">Seleccione **SplashScreen** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="cc585-112">Select **SplashScreen** from the drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc585-113">Si no ve el **SplashScreen** opción, asegúrese de comprobar que está usando [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 o posterior.</span><span class="sxs-lookup"><span data-stu-id="cc585-113">If you do not see the **SplashScreen** option, be sure to check that you are using [!INCLUDE[vs_orcas_long](../../../../includes/vs-orcas-long-md.md)] SP1 or later.</span></span>  
  
6.  <span data-ttu-id="cc585-114">Presione F5 para compilar y ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cc585-114">Press F5 to build and run the application.</span></span>  
  
     <span data-ttu-id="cc585-115">La imagen de la pantalla de presentación aparece en el centro de la pantalla y, a continuación, desaparece cuando aparezca la ventana de la aplicación principal.</span><span class="sxs-lookup"><span data-stu-id="cc585-115">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="cc585-116">Para quitar la pantalla de presentación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="cc585-116">To remove the splash screen from an application</span></span>  
  
1.  <span data-ttu-id="cc585-117">En el Explorador de soluciones, seleccione la imagen de la pantalla de presentación.</span><span class="sxs-lookup"><span data-stu-id="cc585-117">In Solution Explorer, select the splash screen image.</span></span>  
  
2.  <span data-ttu-id="cc585-118">En la ventana Propiedades, establezca la **acción de compilación** a **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="cc585-118">In the Properties window, set the **Build Action** to **None**.</span></span>  
  
### <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="cc585-119">Para quitar la pantalla de presentación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="cc585-119">To remove the splash screen from an application</span></span>  
  
-   <span data-ttu-id="cc585-120">En el Explorador de soluciones, elimine la imagen de la pantalla de presentación.</span><span class="sxs-lookup"><span data-stu-id="cc585-120">In Solution Explorer, delete the splash screen image.</span></span>  
  
-   <span data-ttu-id="cc585-121">Excluya la imagen de la pantalla de presentación del proyecto.</span><span class="sxs-lookup"><span data-stu-id="cc585-121">Exclude the splash screen image from the project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc585-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc585-122">See Also</span></span>  
 <xref:System.Windows.SplashScreen>  
 [<span data-ttu-id="cc585-123">NIB: Cómo: agregar elementos existentes a un proyecto</span><span class="sxs-lookup"><span data-stu-id="cc585-123">NIB:How to: Add Existing Items to a Project</span></span>](http://msdn.microsoft.com/library/15f4cfb7-78ab-457f-9f14-099a25a6a2d3)
