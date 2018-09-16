---
title: 'Tutorial: Hospedar un reloj de WPF en Win32'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: ce8209c89430988f57c211d388c6e73b2dc17004
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45674551"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="17781-102">Tutorial: Hospedar un reloj de WPF en Win32</span><span class="sxs-lookup"><span data-stu-id="17781-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>
<span data-ttu-id="17781-103">Para colocar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] de las aplicaciones, usar <xref:System.Windows.Interop.HwndSource>, que proporciona el HWND que incluye su [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido.</span><span class="sxs-lookup"><span data-stu-id="17781-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="17781-104">En primer lugar cree el <xref:System.Windows.Interop.HwndSource>, proporciónele parámetros similares a los de CreateWindow.</span><span class="sxs-lookup"><span data-stu-id="17781-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span>  <span data-ttu-id="17781-105">Indicar a la <xref:System.Windows.Interop.HwndSource> sobre el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido que desee dentro de él.</span><span class="sxs-lookup"><span data-stu-id="17781-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span>  <span data-ttu-id="17781-106">Por último, debe extraer el HWND de la <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="17781-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="17781-107">En este tutorial se muestra cómo crear un mixto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] aplicación que vuelva a implementar el sistema operativo **propiedades de fecha y hora** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="17781-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="17781-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="17781-108">Prerequisites</span></span>  
 <span data-ttu-id="17781-109">Consulte [WPF e interoperabilidad con Win32](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="17781-109">See [WPF and Win32 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md).</span></span>  
  
## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="17781-110">Cómo usar este tutorial</span><span class="sxs-lookup"><span data-stu-id="17781-110">How to Use This Tutorial</span></span>  
 <span data-ttu-id="17781-111">Este tutorial se centra en los pasos importantes para generar una aplicación de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="17781-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="17781-112">El tutorial está respaldado por un ejemplo, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), pero este ejemplo es reflejo el producto final.</span><span class="sxs-lookup"><span data-stu-id="17781-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="17781-113">En este tutorial se documenta los pasos como si empezara con existente [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] su propio proyecto, quizás un proyecto existente y agregase un hospedado [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="17781-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="17781-114">Puede comparar el producto final con [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="17781-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>  
  
## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="17781-115">Tutorial de Windows Presentation Framework dentro de Win32 (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="17781-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>  
 <span data-ttu-id="17781-116">En el siguiente gráfico se muestra el producto final previsto de este tutorial:</span><span class="sxs-lookup"><span data-stu-id="17781-116">The following graphic shows the intended end product of this tutorial:</span></span>  
  
 <span data-ttu-id="17781-117">![Cuadro de diálogo Propiedades de fecha y hora](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")</span><span class="sxs-lookup"><span data-stu-id="17781-117">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch06.PNG "InteropArch06")</span></span>  
  
 <span data-ttu-id="17781-118">Puede volver a este cuadro de diálogo Crear C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project en [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]y con el editor de cuadro de diálogo para crear lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="17781-118">You can recreate this dialog by creating C++ [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)], and using the dialog editor to create the following:</span></span>  
  
 <span data-ttu-id="17781-119">![Cuadro de diálogo Propiedades de fecha y hora](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")</span><span class="sxs-lookup"><span data-stu-id="17781-119">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch07.PNG "InteropArch07")</span></span>  
  
 <span data-ttu-id="17781-120">(No es necesario usar [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] usar <xref:System.Windows.Interop.HwndSource>, y no es necesario usar C++ para escribir [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programas, pero esto es una manera bastante habitual para hacerlo y se presta bien a una explicación del tutorial paso a paso).</span><span class="sxs-lookup"><span data-stu-id="17781-120">(You do not need to use [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>  
  
 <span data-ttu-id="17781-121">Necesita realizar cinco pasos secundarios concretos para poder colocar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj en el cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="17781-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>  
  
1.  <span data-ttu-id="17781-122">Habilitar la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] proyecto para llamar a código administrado (**/CLR**) cambiando la configuración del proyecto en [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17781-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span></span>  
  
2.  <span data-ttu-id="17781-123">Crear un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> en un archivo DLL independiente.</span><span class="sxs-lookup"><span data-stu-id="17781-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>  
  
3.  <span data-ttu-id="17781-124">Put que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> dentro de un <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="17781-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>  
  
4.  <span data-ttu-id="17781-125">Obtener un HWND para esa <xref:System.Windows.Controls.Page> utilizando el <xref:System.Windows.Interop.HwndSource.Handle%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="17781-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>  
  
5.  <span data-ttu-id="17781-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] para decidir dónde colocar el HWND dentro de la mayor [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] aplicación</span><span class="sxs-lookup"><span data-stu-id="17781-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>  
  
## <a name="clr"></a><span data-ttu-id="17781-127">/clr</span><span class="sxs-lookup"><span data-stu-id="17781-127">/clr</span></span>  
 <span data-ttu-id="17781-128">El primer paso consiste en desactivar esta unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] proyecto en uno que se puede llamar a código administrado.</span><span class="sxs-lookup"><span data-stu-id="17781-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span>  <span data-ttu-id="17781-129">Utilice la opción de compilador/CLR, que se vinculará a los archivos DLL necesarios que desea usar y ajuste el método Main para su uso con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="17781-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
 <span data-ttu-id="17781-130">Para habilitar el uso de código administrado dentro del proyecto de C++: haga doble clic en el proyecto win32clock y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="17781-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span>  <span data-ttu-id="17781-131">En el **General** cambiar de página de propiedades (valor predeterminado), compatibilidad con Common Language Runtime a `/clr`.</span><span class="sxs-lookup"><span data-stu-id="17781-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>  
  
 <span data-ttu-id="17781-132">A continuación, agregue referencias a archivos DLL necesarios para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll y UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="17781-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="17781-133">(si sigue las instrucciones, el sistema operativo se instalará en la unidad C:).</span><span class="sxs-lookup"><span data-stu-id="17781-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>  
  
1.  <span data-ttu-id="17781-134">Haga clic en el proyecto win32clock y seleccione **referencias...** y dentro de ese cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="17781-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>  
  
2.  <span data-ttu-id="17781-135">Haga clic en el proyecto win32clock y seleccione **referencias...** .</span><span class="sxs-lookup"><span data-stu-id="17781-135">Right-click win32clock project and select **References...**.</span></span>  
  
3.  <span data-ttu-id="17781-136">Haga clic en **agregar nueva referencia**, haga clic en la pestaña Examinar, escriba C:\Program de programa\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="17781-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>  
  
4.  <span data-ttu-id="17781-137">Repita el proceso para PresentationFramework.dll: C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="17781-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>  
  
5.  <span data-ttu-id="17781-138">Repita el proceso para WindowsBase.dll: C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="17781-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>  
  
6.  <span data-ttu-id="17781-139">Repita el proceso para UIAutomationTypes.dll: C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="17781-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>  
  
7.  <span data-ttu-id="17781-140">Repita el proceso para UIAutomationProvider.dll: C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span><span class="sxs-lookup"><span data-stu-id="17781-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>  
  
8.  <span data-ttu-id="17781-141">Haga clic en **agregar nueva referencia**, seleccione System.dll y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="17781-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>  
  
9. <span data-ttu-id="17781-142">Haga clic en **Aceptar** para salir de las páginas de propiedades de win32clock para agregar referencias.</span><span class="sxs-lookup"><span data-stu-id="17781-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>  
  
 <span data-ttu-id="17781-143">Por último, agregue el `STAThreadAttribute` a la `_tWinMain` método para su uso con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="17781-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>  
  
```  
[System::STAThreadAttribute]  
int APIENTRY _tWinMain(HINSTANCE hInstance,  
                     HINSTANCE hPrevInstance,  
                     LPTSTR    lpCmdLine,  
                     int       nCmdShow)  
```  
  
 <span data-ttu-id="17781-144">Este atributo indica la [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] que cuando inicializa [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], debe usar un modelo de contenedor uniproceso (STA), que es necesario para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="17781-144">This attribute tells the [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] that when it initializes [!INCLUDE[TLA#tla_com](../../../../includes/tlasharptla-com-md.md)], it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>  
  
## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="17781-145">Cree una página de Windows Presentation Framework</span><span class="sxs-lookup"><span data-stu-id="17781-145">Create a Windows Presentation Framework Page</span></span>  
 <span data-ttu-id="17781-146">A continuación, cree un archivo DLL que define un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="17781-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="17781-147">A menudo resulta más fácil crear el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> como una aplicación independiente y escribir y depurar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] parte de este modo.</span><span class="sxs-lookup"><span data-stu-id="17781-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span>  <span data-ttu-id="17781-148">Una vez hecho, ese proyecto se puede convertir en un archivo DLL haciendo clic con el proyecto, haga clic en **propiedades**, vaya a la aplicación y cambiar el tipo de salida a la biblioteca de clases de Windows.</span><span class="sxs-lookup"><span data-stu-id="17781-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>  
  
 <span data-ttu-id="17781-149">El [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] proyecto dll, a continuación, se puede combinar con el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] proyecto (una solución que contiene dos proyectos), haga doble clic en la solución, seleccione **Agregar\proyecto**.</span><span class="sxs-lookup"><span data-stu-id="17781-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>  
  
 <span data-ttu-id="17781-150">Para usar que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll desde el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] proyecto, deberá agregar una referencia:</span><span class="sxs-lookup"><span data-stu-id="17781-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>  
  
1.  <span data-ttu-id="17781-151">Haga clic en el proyecto win32clock y seleccione **referencias...** .</span><span class="sxs-lookup"><span data-stu-id="17781-151">Right-click win32clock project and select **References...**.</span></span>  
  
2.  <span data-ttu-id="17781-152">Haga clic en **agregar nueva referencia**.</span><span class="sxs-lookup"><span data-stu-id="17781-152">Click **Add New Reference**.</span></span>  
  
3.  <span data-ttu-id="17781-153">Haga clic en la pestaña **Proyectos**.  Seleccione WPFClock y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="17781-153">Click the **Projects** tab.  Select WPFClock, click OK.</span></span>  
  
4.  <span data-ttu-id="17781-154">Haga clic en **Aceptar** para salir de las páginas de propiedades de win32clock para agregar referencias.</span><span class="sxs-lookup"><span data-stu-id="17781-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>  
  
## <a name="hwndsource"></a><span data-ttu-id="17781-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="17781-155">HwndSource</span></span>  
 <span data-ttu-id="17781-156">A continuación, utilice <xref:System.Windows.Interop.HwndSource> para realizar la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> el aspecto de un HWND.</span><span class="sxs-lookup"><span data-stu-id="17781-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span>  <span data-ttu-id="17781-157">Agregue este bloque de código a un archivo de C++:</span><span class="sxs-lookup"><span data-stu-id="17781-157">You add this block of code to a C++ file:</span></span>  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
  
    HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
        HwndSource^ source = gcnew HwndSource(  
            0, // class style  
            WS_VISIBLE | WS_CHILD, // style  
            0, // exstyle  
            x, y, width, height,  
            "hi", // NAME  
            IntPtr(parent)        // parent window   
            );  
  
        UIElement^ page = gcnew WPFClock::Clock();  
        source->RootVisual = page;  
        return (HWND) source->Handle.ToPointer();  
    }  
}  
}  
```  
  
 <span data-ttu-id="17781-158">Se trata de un fragmento de código extenso que podría incluir alguna explicación.</span><span class="sxs-lookup"><span data-stu-id="17781-158">This is a long piece of code that could use some explanation.</span></span>  <span data-ttu-id="17781-159">La primera parte consta de varias cláusulas para que no tenga que completar todas las llamadas:</span><span class="sxs-lookup"><span data-stu-id="17781-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>  
  
```  
namespace ManagedCode  
{  
    using namespace System;  
    using namespace System::Windows;  
    using namespace System::Windows::Interop;  
    using namespace System::Windows::Media;  
```  
  
 <span data-ttu-id="17781-160">Luego, defina una función que crea el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de contenido, coloca una <xref:System.Windows.Interop.HwndSource> en torno a la base de datos y devuelve el HWND:</span><span class="sxs-lookup"><span data-stu-id="17781-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>  
  
```  
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {  
```  
  
 <span data-ttu-id="17781-161">En primer lugar cree un <xref:System.Windows.Interop.HwndSource>, cuyos parámetros son similares a los de CreateWindow:</span><span class="sxs-lookup"><span data-stu-id="17781-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>  
  
```  
HwndSource^ source = gcnew HwndSource(  
    0, // class style  
    WS_VISIBLE | WS_CHILD, // style  
    0, // exstyle  
    x, y, width, height,  
    "hi", // NAME  
    IntPtr(parent) // parent window   
    );  
```  
  
 <span data-ttu-id="17781-162">A continuación, crear el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clase de contenido mediante una llamada a su constructor:</span><span class="sxs-lookup"><span data-stu-id="17781-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>  
  
```  
UIElement^ page = gcnew WPFClock::Clock();  
```  
  
 <span data-ttu-id="17781-163">A continuación, conectar de la página a la <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="17781-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>  
  
```  
source->RootVisual = page;  
```  
  
 <span data-ttu-id="17781-164">Y en la línea final, devuelva el HWND de la <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="17781-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>  
  
```  
return (HWND) source->Handle.ToPointer();  
```  
  
## <a name="positioning-the-hwnd"></a><span data-ttu-id="17781-165">Colocar el HWND</span><span class="sxs-lookup"><span data-stu-id="17781-165">Positioning the Hwnd</span></span>  
 <span data-ttu-id="17781-166">Ahora que tiene un HWND que contiene el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj, es necesario colocar ese HWND dentro de la [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="17781-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span>  <span data-ttu-id="17781-167">Si supiera dónde debe colocar el HWND, bastaría con pasar el tamaño y la ubicación a la `GetHwnd` función definida anteriormente.</span><span class="sxs-lookup"><span data-stu-id="17781-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span>  <span data-ttu-id="17781-168">pero ha usado un archivo de recursos para definir el cuadro de diálogo, por lo que no sabe con certeza dónde están colocados los HWND.</span><span class="sxs-lookup"><span data-stu-id="17781-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span>  <span data-ttu-id="17781-169">Puede usar el [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] editor de cuadro de diálogo para colocar un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] estático controlar donde desea que el reloj ("Insertar reloj aquí") y usarlo para colocar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj.</span><span class="sxs-lookup"><span data-stu-id="17781-169">You can use the [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>  
  
 <span data-ttu-id="17781-170">Administrar WM_INITDIALOG, usa `GetDlgItem` para recuperar el HWND del marcador de posición STATIC:</span><span class="sxs-lookup"><span data-stu-id="17781-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>  
  
```  
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);  
```  
  
 <span data-ttu-id="17781-171">Calcule el tamaño y posición del marcador de posición STATIC, por lo que puede colocar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj en ese lugar:</span><span class="sxs-lookup"><span data-stu-id="17781-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>  
  
 <span data-ttu-id="17781-172">RECT rectángulo;</span><span class="sxs-lookup"><span data-stu-id="17781-172">RECT rectangle;</span></span>  
  
```  
GetWindowRect(placeholder, &rectangle);  
int width = rectangle.right - rectangle.left;  
int height = rectangle.bottom - rectangle.top;  
POINT point;  
point.x = rectangle.left;  
point.y = rectangle.top;  
result = MapWindowPoints(NULL, hDlg, &point, 1);  
```  
  
 <span data-ttu-id="17781-173">Luego, oculte el marcador de posición STATIC:</span><span class="sxs-lookup"><span data-stu-id="17781-173">Then you hide the placeholder STATIC:</span></span>  
  
```  
ShowWindow(placeholder, SW_HIDE);  
```  
  
 <span data-ttu-id="17781-174">Y cree el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj HWND en esa ubicación:</span><span class="sxs-lookup"><span data-stu-id="17781-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>  
  
```  
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);  
```  
  
 <span data-ttu-id="17781-175">Para realizar el tutorial resulte interesante y generar un número real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj, deberá crear un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en este punto de control de reloj.</span><span class="sxs-lookup"><span data-stu-id="17781-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="17781-176">Puede hacerlo principalmente en el marcado, con tan solo unos pocos controladores de eventos en el código subyacente.</span><span class="sxs-lookup"><span data-stu-id="17781-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="17781-177">Puesto que este tutorial es la interoperación y no sobre el diseño de control, complete el código para el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj se proporciona aquí como un bloque de código, sin instrucciones discretas para crearlo o lo que significa cada parte.</span><span class="sxs-lookup"><span data-stu-id="17781-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="17781-178">No dude en experimentar con este código para cambiar el aspecto o la funcionalidad del control.</span><span class="sxs-lookup"><span data-stu-id="17781-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>  
  
 <span data-ttu-id="17781-179">Aquí está el marcado:</span><span class="sxs-lookup"><span data-stu-id="17781-179">Here is the markup:</span></span>  
  
 [!code-xaml[Win32Clock#AllClockXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]  
  
 <span data-ttu-id="17781-180">Y aquí está el código subyacente adjunto:</span><span class="sxs-lookup"><span data-stu-id="17781-180">And here is the accompanying code-behind:</span></span>  
  
 [!code-csharp[Win32Clock#AllClockCS](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]  
  
 <span data-ttu-id="17781-181">El resultado final tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="17781-181">The final result looks like:</span></span>  
  
 <span data-ttu-id="17781-182">![Cuadro de diálogo Propiedades de fecha y hora](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")</span><span class="sxs-lookup"><span data-stu-id="17781-182">![Date and Time Properties dialog box](../../../../docs/framework/wpf/advanced/media/interoparch08.PNG "InteropArch08")</span></span>  
  
 <span data-ttu-id="17781-183">Para comparar el resultado final con el código que produjo esta captura de pantalla, vea [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="17781-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17781-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="17781-184">See Also</span></span>  
 <xref:System.Windows.Interop.HwndSource>  
 [<span data-ttu-id="17781-185">Interoperabilidad de WPF y Win32</span><span class="sxs-lookup"><span data-stu-id="17781-185">WPF and Win32 Interoperation</span></span>](../../../../docs/framework/wpf/advanced/wpf-and-win32-interoperation.md)  
 <span data-ttu-id="17781-186">[Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051) (Ejemplo de interoperación de un reloj de Win32)</span><span class="sxs-lookup"><span data-stu-id="17781-186">[Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051)</span></span>
