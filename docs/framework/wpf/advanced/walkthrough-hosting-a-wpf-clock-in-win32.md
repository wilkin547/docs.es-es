---
title: 'Tutorial: Hospedar un reloj de WPF en Win32'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 42ed51a1a1ce59b6a3cc3319d86d3a7445403ce4
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72919739"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="9bf7b-102">Tutorial: Hospedar un reloj de WPF en Win32</span><span class="sxs-lookup"><span data-stu-id="9bf7b-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>

<span data-ttu-id="9bf7b-103">Para colocar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] aplicaciones, use <xref:System.Windows.Interop.HwndSource>, que proporciona el HWND que contiene el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9bf7b-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="9bf7b-104">En primer lugar, cree el <xref:System.Windows.Interop.HwndSource>, proporcionándole parámetros similares a CreateWindow.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span> <span data-ttu-id="9bf7b-105">A continuación, indique al <xref:System.Windows.Interop.HwndSource> sobre el contenido de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que desea incluir en él.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span> <span data-ttu-id="9bf7b-106">Por último, se obtiene el HWND de la <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="9bf7b-107">En este tutorial se muestra cómo crear una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] mixta dentro de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] aplicación que vuelva a implementar el cuadro de diálogo **propiedades de fecha y hora** del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9bf7b-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9bf7b-108">Prerequisites</span></span>

<span data-ttu-id="9bf7b-109">Consulte [interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="9bf7b-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="9bf7b-110">Cómo usar este tutorial</span><span class="sxs-lookup"><span data-stu-id="9bf7b-110">How to Use This Tutorial</span></span>

<span data-ttu-id="9bf7b-111">Este tutorial se centra en los pasos importantes para generar una aplicación de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="9bf7b-112">El tutorial está respaldado por un ejemplo de [ejemplo de interoperación de reloj de Win32](https://go.microsoft.com/fwlink/?LinkID=160051), pero ese ejemplo refleja el producto final.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="9bf7b-113">En este tutorial se documentan los pasos como si se empezara con un proyecto de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] existente, quizás un proyecto ya existente, y se agregaba un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hospedado a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="9bf7b-114">Puede comparar el producto final con el [ejemplo de interoperación de reloj de Win32](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="9bf7b-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="9bf7b-115">Tutorial de Windows Presentation Framework dentro de Win32 (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="9bf7b-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>

<span data-ttu-id="9bf7b-116">En el siguiente gráfico se muestra el producto final previsto de este tutorial:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-116">The following graphic shows the intended end product of this tutorial:</span></span>

![Captura de pantalla que muestra el cuadro de diálogo Propiedades de fecha y hora.](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

<span data-ttu-id="9bf7b-118">Puede volver a crear este cuadro de diálogo creando C++ un proyecto de Win32 en Visual Studio y usando el editor de cuadros de diálogo para crear lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-118">You can recreate this dialog by creating a C++ Win32 project in Visual Studio, and using the dialog editor to create the following:</span></span>

![Cuadro de diálogo Propiedades de fecha y hora de creación de datos](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

<span data-ttu-id="9bf7b-120">(No es necesario usar Visual Studio para usar <xref:System.Windows.Interop.HwndSource>y no es necesario usar C++ para escribir[!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]programas, pero esta es una manera bastante habitual de hacerlo y se presta bien a una explicación del tutorial de escalonado).</span><span class="sxs-lookup"><span data-stu-id="9bf7b-120">(You do not need to use Visual Studio to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>

<span data-ttu-id="9bf7b-121">Debe realizar cinco subpasos determinados para colocar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj en el cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>

1. <span data-ttu-id="9bf7b-122">Habilite el proyecto de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] para llamar a código administrado ( **/CLR**) cambiando la configuración del proyecto en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in Visual Studio.</span></span>

2. <span data-ttu-id="9bf7b-123">Cree un<xref:System.Windows.Controls.Page> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]en un archivo DLL independiente.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>

3. <span data-ttu-id="9bf7b-124">Coloque el<xref:System.Windows.Controls.Page> de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]dentro de un <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>

4. <span data-ttu-id="9bf7b-125">Obtenga un HWND para ese <xref:System.Windows.Controls.Page> mediante la propiedad <xref:System.Windows.Interop.HwndSource.Handle%2A>.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>

5. <span data-ttu-id="9bf7b-126">Utilice [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] para decidir dónde colocar el HWND dentro de la aplicación de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] más grande.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>

## <a name="clr"></a><span data-ttu-id="9bf7b-127">/clr</span><span class="sxs-lookup"><span data-stu-id="9bf7b-127">/clr</span></span>

<span data-ttu-id="9bf7b-128">El primer paso consiste en convertir este proyecto de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] no administrado en uno que pueda llamar a código administrado.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span> <span data-ttu-id="9bf7b-129">Use la opción del compilador/CLR, que se vinculará a los archivos dll necesarios que desee usar, y ajuste el método Main para su uso con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9bf7b-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>

<span data-ttu-id="9bf7b-130">Para habilitar el uso de código administrado dentro del C++ proyecto: haga clic con el botón derecho en el proyecto win32clock y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span> <span data-ttu-id="9bf7b-131">En la página de propiedades **General** (valor predeterminado), cambie la compatibilidad con Common Language Runtime a `/clr`.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>

<span data-ttu-id="9bf7b-132">A continuación, agregue referencias a los archivos dll necesarios para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore. dll, PresentationFramework. dll, System. dll, WindowsBase. dll, UIAutomationProvider. dll y UIAutomationTypes. dll.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="9bf7b-133">(si sigue las instrucciones, el sistema operativo se instalará en la unidad C:).</span><span class="sxs-lookup"><span data-stu-id="9bf7b-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>

1. <span data-ttu-id="9bf7b-134">Haga clic con el botón secundario en el proyecto win32clock y seleccione **referencias...** , y dentro de ese cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>

2. <span data-ttu-id="9bf7b-135">Haga clic con el botón derecho en proyecto win32clock y seleccione **referencias.** ...</span><span class="sxs-lookup"><span data-stu-id="9bf7b-135">Right-click win32clock project and select **References...**.</span></span>

3. <span data-ttu-id="9bf7b-136">Haga clic en **Agregar nueva referencia**, en la pestaña examinar, escriba C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>

4. <span data-ttu-id="9bf7b-137">Repita el proceso para PresentationFramework.dll: C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>

5. <span data-ttu-id="9bf7b-138">Repita el proceso para WindowsBase.dll: C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>

6. <span data-ttu-id="9bf7b-139">Repita el proceso para UIAutomationTypes.dll: C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>

7. <span data-ttu-id="9bf7b-140">Repita el proceso para UIAutomationProvider.dll: C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>

8. <span data-ttu-id="9bf7b-141">Haga clic en **Agregar nueva referencia**, seleccione System. dll y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>

9. <span data-ttu-id="9bf7b-142">Haga clic en **Aceptar** para salir de las páginas de propiedades de win32clock para agregar referencias.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

 <span data-ttu-id="9bf7b-143">Por último, agregue el `STAThreadAttribute` al método `_tWinMain` para su uso con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

<span data-ttu-id="9bf7b-144">Este atributo indica al Common Language Runtime (CLR) que cuando inicializa el modelo de objetos componentes (COM), debe usar un modelo de apartamento de un solo subproceso (STA), que es necesario para [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (y [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="9bf7b-144">This attribute tells the common language runtime (CLR) that when it initializes Component Object Model (COM), it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>

## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="9bf7b-145">Cree una página de Windows Presentation Framework</span><span class="sxs-lookup"><span data-stu-id="9bf7b-145">Create a Windows Presentation Framework Page</span></span>

<span data-ttu-id="9bf7b-146">A continuación, cree un archivo DLL que defina una [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="9bf7b-147">A menudo es más fácil crear el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> como una aplicación independiente, y escribir y depurar la parte [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] de esa forma.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span> <span data-ttu-id="9bf7b-148">Una vez hecho, ese proyecto se puede convertir en un archivo DLL; para ello, haga clic con el botón secundario en el proyecto, haga clic en **propiedades**, vaya a la aplicación y cambie tipo de salida a biblioteca de clases de Windows.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>

<span data-ttu-id="9bf7b-149">El proyecto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll se puede combinar con el proyecto de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] (una solución que contiene dos proyectos): haga clic con el botón derecho en la solución, seleccione **proyecto de Add\Existing**.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>

<span data-ttu-id="9bf7b-150">Para usar ese [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll del proyecto de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)], debe agregar una referencia:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>

1. <span data-ttu-id="9bf7b-151">Haga clic con el botón derecho en proyecto win32clock y seleccione **referencias.** ...</span><span class="sxs-lookup"><span data-stu-id="9bf7b-151">Right-click win32clock project and select **References...**.</span></span>

2. <span data-ttu-id="9bf7b-152">Haga clic en **Agregar nueva referencia**.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-152">Click **Add New Reference**.</span></span>

3. <span data-ttu-id="9bf7b-153">Haga clic en la pestaña **proyectos** . Seleccione WPFClock y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-153">Click the **Projects** tab. Select WPFClock, click OK.</span></span>

4. <span data-ttu-id="9bf7b-154">Haga clic en **Aceptar** para salir de las páginas de propiedades de win32clock para agregar referencias.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

## <a name="hwndsource"></a><span data-ttu-id="9bf7b-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="9bf7b-155">HwndSource</span></span>

<span data-ttu-id="9bf7b-156">A continuación, use <xref:System.Windows.Interop.HwndSource> para que el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> sea similar a un HWND.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span> <span data-ttu-id="9bf7b-157">Agregue este bloque de código a un archivo de C++:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-157">You add this block of code to a C++ file:</span></span>

```cpp
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

 <span data-ttu-id="9bf7b-158">Se trata de un fragmento de código extenso que podría incluir alguna explicación.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-158">This is a long piece of code that could use some explanation.</span></span> <span data-ttu-id="9bf7b-159">La primera parte consta de varias cláusulas para que no tenga que completar todas las llamadas:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 <span data-ttu-id="9bf7b-160">A continuación, se define una función que crea el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] contenido, coloca un <xref:System.Windows.Interop.HwndSource> alrededor y devuelve el HWND:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

<span data-ttu-id="9bf7b-161">En primer lugar, cree una <xref:System.Windows.Interop.HwndSource>, cuyos parámetros sean similares a los de CreateWindow:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>

```cpp
HwndSource^ source = gcnew HwndSource(
    0, // class style
    WS_VISIBLE | WS_CHILD, // style
    0, // exstyle
    x, y, width, height,
    "hi", // NAME
    IntPtr(parent) // parent window
);
```

<span data-ttu-id="9bf7b-162">A continuación, cree la clase de contenido [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] llamando a su constructor:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

<span data-ttu-id="9bf7b-163">A continuación, conecte la página al <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
source->RootVisual = page;
```

 <span data-ttu-id="9bf7b-164">Y, en la línea final, devuelva el HWND para el <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a><span data-ttu-id="9bf7b-165">Colocar el HWND</span><span class="sxs-lookup"><span data-stu-id="9bf7b-165">Positioning the Hwnd</span></span>

<span data-ttu-id="9bf7b-166">Ahora que tiene un HWND que contiene el reloj [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], debe colocar ese HWND dentro del cuadro de diálogo [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9bf7b-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span> <span data-ttu-id="9bf7b-167">Si sabía dónde colocar el HWND, simplemente pasaría ese tamaño y ubicación a la función de `GetHwnd` que definió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span> <span data-ttu-id="9bf7b-168">pero ha usado un archivo de recursos para definir el cuadro de diálogo, por lo que no sabe con certeza dónde están colocados los HWND.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span> <span data-ttu-id="9bf7b-169">Puede usar el editor de cuadros de diálogo de Visual Studio para colocar un [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] control estático en el que desea que el reloj ("Inserte el reloj aquí") y usarlo para colocar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-169">You can use the Visual Studio dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>

<span data-ttu-id="9bf7b-170">Cuando se controla WM_INITDIALOG, se usa `GetDlgItem` para recuperar el HWND para el marcador de posición STATIC:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

<span data-ttu-id="9bf7b-171">A continuación, calcula el tamaño y la posición del marcador de posición estático, de modo que puede colocar el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj en ese lugar:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>

<span data-ttu-id="9bf7b-172">RECT rectángulo;</span><span class="sxs-lookup"><span data-stu-id="9bf7b-172">RECT rectangle;</span></span>

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

<span data-ttu-id="9bf7b-173">Luego, oculte el marcador de posición STATIC:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-173">Then you hide the placeholder STATIC:</span></span>

```cpp
ShowWindow(placeholder, SW_HIDE);
```

<span data-ttu-id="9bf7b-174">Y crean el HWND de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj en esa ubicación:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

<span data-ttu-id="9bf7b-175">Para que el tutorial le resulte interesante y para generar un reloj real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], deberá crear un control de reloj de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] en este momento.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="9bf7b-176">Puede hacerlo principalmente en el marcado, con tan solo unos pocos controladores de eventos en el código subyacente.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="9bf7b-177">Dado que este tutorial trata sobre la interoperación y no sobre el diseño del control, el código completo para el reloj de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] se proporciona aquí como un bloque de código, sin instrucciones discretas para crearlo o lo que significa cada parte.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="9bf7b-178">No dude en experimentar con este código para cambiar el aspecto o la funcionalidad del control.</span><span class="sxs-lookup"><span data-stu-id="9bf7b-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>

<span data-ttu-id="9bf7b-179">Aquí está el marcado:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-179">Here is the markup:</span></span>

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

<span data-ttu-id="9bf7b-180">Y aquí está el código subyacente adjunto:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-180">And here is the accompanying code-behind:</span></span>

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

<span data-ttu-id="9bf7b-181">El resultado final tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="9bf7b-181">The final result looks like:</span></span>

![Cuadro de diálogo Propiedades de fecha y hora de resultado final](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

<span data-ttu-id="9bf7b-183">Para comparar el resultado final con el código que generó esta captura de pantalla, vea [ejemplo de interoperación de reloj de Win32](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="9bf7b-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="see-also"></a><span data-ttu-id="9bf7b-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="9bf7b-184">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="9bf7b-185">Interoperabilidad de WPF y Win32</span><span class="sxs-lookup"><span data-stu-id="9bf7b-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- <span data-ttu-id="9bf7b-186">[Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051) (Ejemplo de interoperación de un reloj de Win32)</span><span class="sxs-lookup"><span data-stu-id="9bf7b-186">[Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051)</span></span>
