---
title: 'Tutorial: Hospedar un reloj de WPF en Win32'
ms.date: 03/30/2017
helpviewer_keywords:
- interoperability [WPF], tutorials
- Win32 code [WPF], WPF interoperation
- interoperability [WPF], Win32
ms.assetid: 555e55a7-0851-4ec8-b1c6-0acba7e9b648
ms.openlocfilehash: 27e1a2e88beeacf8c2cd98f61b11542ee2341e8f
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433977"
---
# <a name="walkthrough-hosting-a-wpf-clock-in-win32"></a><span data-ttu-id="07e8e-102">Tutorial: Hospedar un reloj de WPF en Win32</span><span class="sxs-lookup"><span data-stu-id="07e8e-102">Walkthrough: Hosting a WPF Clock in Win32</span></span>

<span data-ttu-id="07e8e-103">Para colocar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] de las aplicaciones <xref:System.Windows.Interop.HwndSource>, use, que proporciona el HWND que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] incluye el contenido.</span><span class="sxs-lookup"><span data-stu-id="07e8e-103">To put [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] applications, use <xref:System.Windows.Interop.HwndSource>, which provides the HWND that contains your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span> <span data-ttu-id="07e8e-104">En primer lugar, <xref:System.Windows.Interop.HwndSource>cree el, y asígnele parámetros similares a CreateWindow.</span><span class="sxs-lookup"><span data-stu-id="07e8e-104">First you create the <xref:System.Windows.Interop.HwndSource>, giving it parameters similar to CreateWindow.</span></span> <span data-ttu-id="07e8e-105">A continuación, se <xref:System.Windows.Interop.HwndSource> indica a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] sobre el contenido que se desea incluir en él.</span><span class="sxs-lookup"><span data-stu-id="07e8e-105">Then you tell the <xref:System.Windows.Interop.HwndSource> about the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content you want inside it.</span></span> <span data-ttu-id="07e8e-106">Por último, se obtiene el HWND de la <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="07e8e-106">Finally, you get the HWND out of the <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="07e8e-107">En este tutorial se muestra cómo crear una aplicación [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dentro [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] de una mezcla que vuelva a implementar el cuadro de diálogo **propiedades de fecha y hora** del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="07e8e-107">This walkthrough illustrates how to create a mixed [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] inside [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application that reimplements the operating system **Date and Time Properties** dialog.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="07e8e-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="07e8e-108">Prerequisites</span></span>

<span data-ttu-id="07e8e-109">Consulte [interoperabilidad de WPF y Win32](wpf-and-win32-interoperation.md).</span><span class="sxs-lookup"><span data-stu-id="07e8e-109">See [WPF and Win32 Interoperation](wpf-and-win32-interoperation.md).</span></span>

## <a name="how-to-use-this-tutorial"></a><span data-ttu-id="07e8e-110">Cómo usar este tutorial</span><span class="sxs-lookup"><span data-stu-id="07e8e-110">How to Use This Tutorial</span></span>

<span data-ttu-id="07e8e-111">Este tutorial se centra en los pasos importantes para generar una aplicación de interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="07e8e-111">This tutorial concentrates on the important steps of producing an interoperation application.</span></span> <span data-ttu-id="07e8e-112">El tutorial está respaldado por un ejemplo de [ejemplo](https://go.microsoft.com/fwlink/?LinkID=160051)de interoperación de reloj de Win32, pero ese ejemplo refleja el producto final.</span><span class="sxs-lookup"><span data-stu-id="07e8e-112">The tutorial is backed by a sample, [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051), but that sample is reflective of the end product.</span></span> <span data-ttu-id="07e8e-113">En este tutorial se documentan los pasos como si se empezara [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] con un proyecto existente, quizás un proyecto ya existente, y se agregaba un hospedado [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="07e8e-113">This tutorial documents the steps as if you were starting with an existing [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project of your own, perhaps a pre-existing project, and you were adding a hosted [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] to your application.</span></span> <span data-ttu-id="07e8e-114">Puede comparar el producto final con el [ejemplo](https://go.microsoft.com/fwlink/?LinkID=160051)de interoperación de reloj de Win32.</span><span class="sxs-lookup"><span data-stu-id="07e8e-114">You can compare your end product with [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="a-walkthrough-of-windows-presentation-framework-inside-win32-hwndsource"></a><span data-ttu-id="07e8e-115">Tutorial de Windows Presentation Framework dentro de Win32 (HwndSource)</span><span class="sxs-lookup"><span data-stu-id="07e8e-115">A Walkthrough of Windows Presentation Framework Inside Win32 (HwndSource)</span></span>

<span data-ttu-id="07e8e-116">En el siguiente gráfico se muestra el producto final previsto de este tutorial:</span><span class="sxs-lookup"><span data-stu-id="07e8e-116">The following graphic shows the intended end product of this tutorial:</span></span>

![Captura de pantalla que muestra el cuadro de diálogo Propiedades de fecha y hora.](./media/walkthrough-hosting-a-wpf-clock-in-win32/date-time-properties-dialog.png)

<span data-ttu-id="07e8e-118">Puede volver a crear este cuadro de diálogo creando C++ un proyecto de Win32 en Visual Studio y usando el editor de cuadros de diálogo para crear lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="07e8e-118">You can recreate this dialog by creating a C++ Win32 project in Visual Studio, and using the dialog editor to create the following:</span></span>

![Cuadro de diálogo Propiedades de fecha y hora de creación de datos](./media/walkthrough-hosting-a-wpf-clock-in-win32/recreated-date-time-properties-dialog.png)

<span data-ttu-id="07e8e-120">(No [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] es necesario usar para usar <xref:System.Windows.Interop.HwndSource>y no es necesario usar C++ para escribir [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programas, pero esta es una manera bastante habitual de hacerlo y se presta bien a una explicación del tutorial de escalonado).</span><span class="sxs-lookup"><span data-stu-id="07e8e-120">(You do not need to use [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] to use <xref:System.Windows.Interop.HwndSource>, and you do not need to use C++ to write [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] programs, but this is a fairly typical way to do it, and lends itself well to a stepwise tutorial explanation).</span></span>

<span data-ttu-id="07e8e-121">Debe realizar cinco subpasos determinados para colocar un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj en el cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="07e8e-121">You need to accomplish five particular substeps in order to put a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock into the dialog:</span></span>

1. <span data-ttu-id="07e8e-122">Habilite el [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] proyecto para que llame a código administrado ( **/CLR**) cambiando la configuración [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)]del proyecto en.</span><span class="sxs-lookup"><span data-stu-id="07e8e-122">Enable your [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project to call managed code (**/clr**) by changing project settings in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)].</span></span>

2. <span data-ttu-id="07e8e-123">Cree un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> en un archivo dll independiente.</span><span class="sxs-lookup"><span data-stu-id="07e8e-123">Create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> in a separate DLL.</span></span>

3. <span data-ttu-id="07e8e-124">Colóquelo dentro [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> de.<xref:System.Windows.Interop.HwndSource></span><span class="sxs-lookup"><span data-stu-id="07e8e-124">Put that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> inside an <xref:System.Windows.Interop.HwndSource>.</span></span>

4. <span data-ttu-id="07e8e-125">Obtenga un HWND para que <xref:System.Windows.Controls.Page> use la <xref:System.Windows.Interop.HwndSource.Handle%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="07e8e-125">Get an HWND for that <xref:System.Windows.Controls.Page> using the <xref:System.Windows.Interop.HwndSource.Handle%2A> property.</span></span>

5. <span data-ttu-id="07e8e-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] para decidir dónde colocar el HWND dentro de la aplicación [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] más grande</span><span class="sxs-lookup"><span data-stu-id="07e8e-126">Use [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] to decide where to place the HWND within the larger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] application</span></span>

## <a name="clr"></a><span data-ttu-id="07e8e-127">/clr</span><span class="sxs-lookup"><span data-stu-id="07e8e-127">/clr</span></span>

<span data-ttu-id="07e8e-128">El primer paso consiste en convertir este [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] proyecto no administrado en uno que pueda llamar a código administrado.</span><span class="sxs-lookup"><span data-stu-id="07e8e-128">The first step is to turn this unmanaged [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project into one that can call managed code.</span></span> <span data-ttu-id="07e8e-129">Utilice la opción del compilador/CLR, que se vinculará a los archivos dll necesarios que desee usar, y ajuste el método Main [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]para su uso con.</span><span class="sxs-lookup"><span data-stu-id="07e8e-129">You use the /clr compiler option, which will link to the necessary DLLs you want to use, and adjust the Main method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)].</span></span>

<span data-ttu-id="07e8e-130">Para habilitar el uso de código administrado dentro del C++ proyecto: Haga clic con el botón derecho en el proyecto win32clock y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="07e8e-130">To enable the use of managed code inside the C++ project: Right-click on win32clock project and select **Properties**.</span></span> <span data-ttu-id="07e8e-131">En la página de propiedades **General** (valor predeterminado), cambie compatibilidad con Common Language `/clr`Runtime a.</span><span class="sxs-lookup"><span data-stu-id="07e8e-131">On the **General** property page (the default), change Common Language Runtime support to `/clr`.</span></span>

<span data-ttu-id="07e8e-132">A continuación, agregue referencias a los archivos [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]dll necesarios para: PresentationCore. dll, PresentationFramework. dll, System. dll, WindowsBase. dll, UIAutomationProvider. dll y UIAutomationTypes. dll.</span><span class="sxs-lookup"><span data-stu-id="07e8e-132">Next, add references to DLLs necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]: PresentationCore.dll, PresentationFramework.dll, System.dll, WindowsBase.dll, UIAutomationProvider.dll, and UIAutomationTypes.dll.</span></span> <span data-ttu-id="07e8e-133">(si sigue las instrucciones, el sistema operativo se instalará en la unidad C:).</span><span class="sxs-lookup"><span data-stu-id="07e8e-133">(Following instructions assume the operating system is installed on C: drive.)</span></span>

1. <span data-ttu-id="07e8e-134">Haga clic con el botón secundario en el proyecto win32clock y seleccione **referencias...** , y dentro de ese cuadro de diálogo:</span><span class="sxs-lookup"><span data-stu-id="07e8e-134">Right-click win32clock project and select **References...**, and inside that dialog:</span></span>

2. <span data-ttu-id="07e8e-135">Haga clic con el botón derecho en proyecto win32clock y seleccione **referencias.** ...</span><span class="sxs-lookup"><span data-stu-id="07e8e-135">Right-click win32clock project and select **References...**.</span></span>

3. <span data-ttu-id="07e8e-136">Haga clic en **Agregar nueva referencia**, en la pestaña examinar, escriba C:\Archivos de programa\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="07e8e-136">Click **Add New Reference**, click Browse tab, enter C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationCore.dll, and click OK.</span></span>

4. <span data-ttu-id="07e8e-137">Repita el procedimiento para PresentationFramework. dll: C:\Archivos de Programa\reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span><span class="sxs-lookup"><span data-stu-id="07e8e-137">Repeat for PresentationFramework.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationFramework.dll.</span></span>

5. <span data-ttu-id="07e8e-138">Repita el procedimiento para WindowsBase. dll: C:\Archivos de Programa\reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span><span class="sxs-lookup"><span data-stu-id="07e8e-138">Repeat for WindowsBase.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\WindowsBase.dll.</span></span>

6. <span data-ttu-id="07e8e-139">Repita el procedimiento para UIAutomationTypes. dll: C:\Archivos de Programa\reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span><span class="sxs-lookup"><span data-stu-id="07e8e-139">Repeat for UIAutomationTypes.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationTypes.dll.</span></span>

7. <span data-ttu-id="07e8e-140">Repita el procedimiento para UIAutomationProvider. dll: C:\Archivos de Programa\reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span><span class="sxs-lookup"><span data-stu-id="07e8e-140">Repeat for UIAutomationProvider.dll: C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\UIAutomationProvider.dll.</span></span>

8. <span data-ttu-id="07e8e-141">Haga clic en **Agregar nueva referencia**, seleccione System. dll y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="07e8e-141">Click **Add New Reference**, select System.dll, and click **OK**.</span></span>

9. <span data-ttu-id="07e8e-142">Haga clic en **Aceptar** para salir de las páginas de propiedades de win32clock para agregar referencias.</span><span class="sxs-lookup"><span data-stu-id="07e8e-142">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

 <span data-ttu-id="07e8e-143">Por último, agregue `STAThreadAttribute` el `_tWinMain` al método para su uso [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]con:</span><span class="sxs-lookup"><span data-stu-id="07e8e-143">Finally, add the `STAThreadAttribute` to the `_tWinMain` method for use with [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]:</span></span>

```cpp
[System::STAThreadAttribute]
int APIENTRY _tWinMain(HINSTANCE hInstance,
                     HINSTANCE hPrevInstance,
                     LPTSTR    lpCmdLine,
                     int       nCmdShow)
```

<span data-ttu-id="07e8e-144">Este atributo indica al Common Language Runtime (CLR) que cuando inicializa el modelo de objetos componentes (com), debe usar un modelo de apartamento de un solo subproceso (STA), que es [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] necesario para [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)](y).</span><span class="sxs-lookup"><span data-stu-id="07e8e-144">This attribute tells the common language runtime (CLR) that when it initializes Component Object Model (COM), it should use a single threaded apartment model (STA), which is necessary for [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] (and [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]).</span></span>

## <a name="create-a-windows-presentation-framework-page"></a><span data-ttu-id="07e8e-145">Cree una página de Windows Presentation Framework</span><span class="sxs-lookup"><span data-stu-id="07e8e-145">Create a Windows Presentation Framework Page</span></span>

<span data-ttu-id="07e8e-146">A continuación, se crea un archivo DLL que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]define un. <xref:System.Windows.Controls.Page></span><span class="sxs-lookup"><span data-stu-id="07e8e-146">Next, you create a DLL that defines a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="07e8e-147">A menudo es más fácil crear el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> como una aplicación independiente y escribir y depurar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la parte de ese modo.</span><span class="sxs-lookup"><span data-stu-id="07e8e-147">It’s often easiest to create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> as a standalone application, and write and debug the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] portion that way.</span></span> <span data-ttu-id="07e8e-148">Una vez hecho, ese proyecto se puede convertir en un archivo DLL; para ello, haga clic con el botón secundario en el proyecto, haga clic en **propiedades**, vaya a la aplicación y cambie tipo de salida a biblioteca de clases de Windows.</span><span class="sxs-lookup"><span data-stu-id="07e8e-148">Once done, that project can be turned into a DLL by right-clicking the project, clicking on **Properties**, going to the Application, and changing Output type to Windows Class Library.</span></span>

<span data-ttu-id="07e8e-149">Después [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , el proyecto dll se puede combinar con [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] el proyecto (una solución que contiene dos proyectos): haga clic con el botón derecho en la solución, seleccione **proyecto de Add\Existing**.</span><span class="sxs-lookup"><span data-stu-id="07e8e-149">The [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll project can then be combined with the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project (one solution that contains two projects) – right-click on the solution, select **Add\Existing Project**.</span></span>

<span data-ttu-id="07e8e-150">Para usar ese [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] archivo dll desde [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] el proyecto, debe agregar una referencia:</span><span class="sxs-lookup"><span data-stu-id="07e8e-150">To use that [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] dll from the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] project, you need to add a reference:</span></span>

1. <span data-ttu-id="07e8e-151">Haga clic con el botón derecho en proyecto win32clock y seleccione **referencias.** ...</span><span class="sxs-lookup"><span data-stu-id="07e8e-151">Right-click win32clock project and select **References...**.</span></span>

2. <span data-ttu-id="07e8e-152">Haga clic en **Agregar nueva referencia**.</span><span class="sxs-lookup"><span data-stu-id="07e8e-152">Click **Add New Reference**.</span></span>

3. <span data-ttu-id="07e8e-153">Haga clic en la pestaña **Proyectos**. Seleccione WPFClock y haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="07e8e-153">Click the **Projects** tab. Select WPFClock, click OK.</span></span>

4. <span data-ttu-id="07e8e-154">Haga clic en **Aceptar** para salir de las páginas de propiedades de win32clock para agregar referencias.</span><span class="sxs-lookup"><span data-stu-id="07e8e-154">Click **OK** to exit the win32clock Property Pages for adding references.</span></span>

## <a name="hwndsource"></a><span data-ttu-id="07e8e-155">HwndSource</span><span class="sxs-lookup"><span data-stu-id="07e8e-155">HwndSource</span></span>

<span data-ttu-id="07e8e-156">A continuación, use <xref:System.Windows.Interop.HwndSource> para que el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.Page> aspecto sea un HWND.</span><span class="sxs-lookup"><span data-stu-id="07e8e-156">Next, you use <xref:System.Windows.Interop.HwndSource> to make the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.Page> look like an HWND.</span></span> <span data-ttu-id="07e8e-157">Agregue este bloque de código a un archivo de C++:</span><span class="sxs-lookup"><span data-stu-id="07e8e-157">You add this block of code to a C++ file:</span></span>

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

 <span data-ttu-id="07e8e-158">Se trata de un fragmento de código extenso que podría incluir alguna explicación.</span><span class="sxs-lookup"><span data-stu-id="07e8e-158">This is a long piece of code that could use some explanation.</span></span> <span data-ttu-id="07e8e-159">La primera parte consta de varias cláusulas para que no tenga que completar todas las llamadas:</span><span class="sxs-lookup"><span data-stu-id="07e8e-159">The first part is various clauses so that you do not need to fully qualify all the calls:</span></span>

```cpp
namespace ManagedCode
{
    using namespace System;
    using namespace System::Windows;
    using namespace System::Windows::Interop;
    using namespace System::Windows::Media;
```

 <span data-ttu-id="07e8e-160">A continuación, se define una función que [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] crea el contenido, <xref:System.Windows.Interop.HwndSource> coloca una alrededor y devuelve el HWND:</span><span class="sxs-lookup"><span data-stu-id="07e8e-160">Then you define a function that creates the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content, puts an <xref:System.Windows.Interop.HwndSource> around it, and returns the HWND:</span></span>

```cpp
HWND GetHwnd(HWND parent, int x, int y, int width, int height) {
```

<span data-ttu-id="07e8e-161">Primero se crea un <xref:System.Windows.Interop.HwndSource>, cuyos parámetros son similares a los de CreateWindow:</span><span class="sxs-lookup"><span data-stu-id="07e8e-161">First you create an <xref:System.Windows.Interop.HwndSource>, whose parameters are similar to CreateWindow:</span></span>

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

<span data-ttu-id="07e8e-162">A continuación, cree [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] la clase de contenido llamando a su constructor:</span><span class="sxs-lookup"><span data-stu-id="07e8e-162">Then you create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content class by calling its constructor:</span></span>

```cpp
UIElement^ page = gcnew WPFClock::Clock();
```

<span data-ttu-id="07e8e-163">A continuación, conecte la página a <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="07e8e-163">You then connect the page to the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
source->RootVisual = page;
```

 <span data-ttu-id="07e8e-164">Y en la línea final, devuelva el HWND para <xref:System.Windows.Interop.HwndSource>:</span><span class="sxs-lookup"><span data-stu-id="07e8e-164">And in the final line, return the HWND for the <xref:System.Windows.Interop.HwndSource>:</span></span>

```cpp
return (HWND) source->Handle.ToPointer();
```

## <a name="positioning-the-hwnd"></a><span data-ttu-id="07e8e-165">Colocar el HWND</span><span class="sxs-lookup"><span data-stu-id="07e8e-165">Positioning the Hwnd</span></span>

<span data-ttu-id="07e8e-166">Ahora que tiene un HWND que contiene el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] reloj, debe colocar ese HWND en el cuadro de [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] diálogo.</span><span class="sxs-lookup"><span data-stu-id="07e8e-166">Now that you have an HWND that contains the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you need to put that HWND inside the [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dialog.</span></span> <span data-ttu-id="07e8e-167">Si sabía dónde colocar el HWND, simplemente pasaría ese tamaño y ubicación a la `GetHwnd` función que definió anteriormente.</span><span class="sxs-lookup"><span data-stu-id="07e8e-167">If you knew just where to put the HWND, you would just pass that size and location to the `GetHwnd` function you defined earlier.</span></span> <span data-ttu-id="07e8e-168">pero ha usado un archivo de recursos para definir el cuadro de diálogo, por lo que no sabe con certeza dónde están colocados los HWND.</span><span class="sxs-lookup"><span data-stu-id="07e8e-168">But you used a resource file to define the dialog, so you are not exactly sure where any of the HWNDs are positioned.</span></span> <span data-ttu-id="07e8e-169">Puede usar el [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] editor de cuadros de diálogo para [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] colocar un control estático en el que desea que el reloj ("Inserte el reloj aquí") y usarlo para colocar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el reloj.</span><span class="sxs-lookup"><span data-stu-id="07e8e-169">You can use the [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] dialog editor to put a [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] STATIC control where you want the clock to go ("Insert clock here"), and use that to position the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock.</span></span>

<span data-ttu-id="07e8e-170">Donde se controla WM_INITDIALOG, se usa `GetDlgItem` para recuperar el HWND para el marcador de posición Static:</span><span class="sxs-lookup"><span data-stu-id="07e8e-170">Where you handle WM_INITDIALOG, you use `GetDlgItem` to retrieve the HWND for the placeholder STATIC:</span></span>

```cpp
HWND placeholder = GetDlgItem(hDlg, IDC_CLOCK);
```

<span data-ttu-id="07e8e-171">A continuación, calcula el tamaño y la posición del marcador de posición estático, de modo [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] que puede colocar el reloj en ese lugar:</span><span class="sxs-lookup"><span data-stu-id="07e8e-171">You then calculate the size and position of that placeholder STATIC, so you can put the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock in that place:</span></span>

<span data-ttu-id="07e8e-172">RECT rectángulo;</span><span class="sxs-lookup"><span data-stu-id="07e8e-172">RECT rectangle;</span></span>

```cpp
GetWindowRect(placeholder, &rectangle);
int width = rectangle.right - rectangle.left;
int height = rectangle.bottom - rectangle.top;
POINT point;
point.x = rectangle.left;
point.y = rectangle.top;
result = MapWindowPoints(NULL, hDlg, &point, 1);
```

<span data-ttu-id="07e8e-173">Luego, oculte el marcador de posición STATIC:</span><span class="sxs-lookup"><span data-stu-id="07e8e-173">Then you hide the placeholder STATIC:</span></span>

```cpp
ShowWindow(placeholder, SW_HIDE);
```

<span data-ttu-id="07e8e-174">Y crean el [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND del reloj en esa ubicación:</span><span class="sxs-lookup"><span data-stu-id="07e8e-174">And create the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock HWND in that location:</span></span>

```cpp
HWND clock = ManagedCode::GetHwnd(hDlg, point.x, point.y, width, height);
```

<span data-ttu-id="07e8e-175">Para que el tutorial le resulte interesante y para generar [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] un reloj real, deberá crear un [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] control de reloj en este momento.</span><span class="sxs-lookup"><span data-stu-id="07e8e-175">To make the tutorial interesting, and to produce a real [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock, you will need to create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock control at this point.</span></span> <span data-ttu-id="07e8e-176">Puede hacerlo principalmente en el marcado, con tan solo unos pocos controladores de eventos en el código subyacente.</span><span class="sxs-lookup"><span data-stu-id="07e8e-176">You can do so mostly in markup, with just a few event handlers in code-behind.</span></span> <span data-ttu-id="07e8e-177">Dado que este tutorial trata sobre la interoperación y no sobre el diseño del control, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] el código completo del reloj se proporciona aquí como un bloque de código, sin instrucciones discretas para crearlo o lo que significa cada parte.</span><span class="sxs-lookup"><span data-stu-id="07e8e-177">Since this tutorial is about interoperation and not about control design, complete code for the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] clock is provided here as a code block, without discrete instructions for building it up or what each part means.</span></span> <span data-ttu-id="07e8e-178">No dude en experimentar con este código para cambiar el aspecto o la funcionalidad del control.</span><span class="sxs-lookup"><span data-stu-id="07e8e-178">Feel free to experiment with this code to change the look and feel or functionality of the control.</span></span>

<span data-ttu-id="07e8e-179">Aquí está el marcado:</span><span class="sxs-lookup"><span data-stu-id="07e8e-179">Here is the markup:</span></span>

[!code-xaml[Win32Clock#AllClockXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml#allclockxaml)]

<span data-ttu-id="07e8e-180">Y aquí está el código subyacente adjunto:</span><span class="sxs-lookup"><span data-stu-id="07e8e-180">And here is the accompanying code-behind:</span></span>

[!code-csharp[Win32Clock#AllClockCS](~/samples/snippets/csharp/VS_Snippets_Wpf/Win32Clock/CS/Clock.xaml.cs#allclockcs)]

<span data-ttu-id="07e8e-181">El resultado final tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="07e8e-181">The final result looks like:</span></span>

![Cuadro de diálogo Propiedades de fecha y hora de resultado final](./media/walkthrough-hosting-a-wpf-clock-in-win32/final-result-date-time-properties-dialog.png)

<span data-ttu-id="07e8e-183">Para comparar el resultado final con el código que generó esta captura de pantalla, vea ejemplo de interoperación de [reloj de Win32](https://go.microsoft.com/fwlink/?LinkID=160051).</span><span class="sxs-lookup"><span data-stu-id="07e8e-183">To compare your end result to the code that produced this screenshot, see [Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051).</span></span>

## <a name="see-also"></a><span data-ttu-id="07e8e-184">Vea también</span><span class="sxs-lookup"><span data-stu-id="07e8e-184">See also</span></span>

- <xref:System.Windows.Interop.HwndSource>
- [<span data-ttu-id="07e8e-185">Interoperabilidad de WPF y Win32</span><span class="sxs-lookup"><span data-stu-id="07e8e-185">WPF and Win32 Interoperation</span></span>](wpf-and-win32-interoperation.md)
- <span data-ttu-id="07e8e-186">[Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051) (Ejemplo de interoperación de un reloj de Win32)</span><span class="sxs-lookup"><span data-stu-id="07e8e-186">[Win32 Clock Interoperation Sample](https://go.microsoft.com/fwlink/?LinkID=160051)</span></span>
