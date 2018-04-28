---
title: 'Cómo: Agregar funciones de explorador Web a una aplicación de Windows Forms'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- WebBrowser control [Windows Forms], adding Web browser capabilities to your application
- WebBrowser control [Windows Forms], examples
- Web browsers [.NET Framework], adding to Windows Forms
- examples [Windows Forms], WebBrowser control
- Windows Forms, adding Web browser functionality
ms.assetid: 3871f072-b57a-435b-9976-e5da28df04a7
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: fb5809a7932df2950b2badc983adeded1b3f0aa5
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-add-web-browser-capabilities-to-a-windows-forms-application"></a><span data-ttu-id="fdfd6-102">Cómo: Agregar funciones de explorador Web a una aplicación de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fdfd6-102">How to: Add Web Browser Capabilities to a Windows Forms Application</span></span>
<span data-ttu-id="fdfd6-103">Con el control <xref:System.Windows.Forms.WebBrowser>, puede agregar funcionalidades del explorador web a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fdfd6-103">With the <xref:System.Windows.Forms.WebBrowser> control, you can add Web browser functionality to your application.</span></span> <span data-ttu-id="fdfd6-104">De forma predeterminada, el control funciona como un explorador web.</span><span class="sxs-lookup"><span data-stu-id="fdfd6-104">The control works like a Web browser by default.</span></span> <span data-ttu-id="fdfd6-105">Después de cargar una dirección URL inicial estableciendo la propiedad <xref:System.Windows.Forms.WebBrowser.Url%2A>, puede navegar haciendo clic en hipervínculos o utilizando métodos abreviados de teclado para avanzar y retroceder por el historial de navegación.</span><span class="sxs-lookup"><span data-stu-id="fdfd6-105">After you load an initial URL by setting the <xref:System.Windows.Forms.WebBrowser.Url%2A> property, you can navigate by clicking hyperlinks or by using keyboard shortcuts to move backward and forward through navigation history.</span></span> <span data-ttu-id="fdfd6-106">De forma predeterminada, puede acceder a funcionalidades adicionales del explorador a través del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="fdfd6-106">By default, you can access additional browser functionality through the right-click shortcut menu.</span></span> <span data-ttu-id="fdfd6-107">También puede abrir documentos nuevos colocándolos en el control.</span><span class="sxs-lookup"><span data-stu-id="fdfd6-107">You can also open new documents by dropping them onto the control.</span></span> <span data-ttu-id="fdfd6-108">El control <xref:System.Windows.Forms.WebBrowser> también tiene varias propiedades, métodos y eventos que puede utilizar para implementar características de interfaz de usuario similares a las que se encuentran en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="fdfd6-108">The <xref:System.Windows.Forms.WebBrowser> control also has several properties, methods, and events that you can use to implement user interface features similar to those found in Internet Explorer.</span></span>  
  
 <span data-ttu-id="fdfd6-109">En el ejemplo de código siguiente, se implementa una barra de direcciones, los botones de exploración típicos, un menú **Archivo**, una barra de estado y una barra de título que muestra el título de la página actual.</span><span class="sxs-lookup"><span data-stu-id="fdfd6-109">The following code example implements an address bar, typical browser buttons, a **File** menu, a status bar, and a title bar that displays the current page title.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdfd6-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fdfd6-110">Example</span></span>  
 [!code-cpp[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CPP/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fdfd6-111">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="fdfd6-111">Compiling the Code</span></span>  
 <span data-ttu-id="fdfd6-112">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="fdfd6-112">This example requires:</span></span>  
  
-   <span data-ttu-id="fdfd6-113">Referencias a los ensamblados `System,``System.Drawing` y `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="fdfd6-113">References to the `System,``System.Drawing`, and `System.Windows.Forms` assemblies.</span></span>  
  
 <span data-ttu-id="fdfd6-114">Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos de Visual Basic o Visual C#, vea [compilar desde la línea de comandos](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) o [Command-Line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="fdfd6-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="fdfd6-115">También puede compilar este ejemplo en Visual Studio pegando el código en un nuevo proyecto.</span><span class="sxs-lookup"><span data-stu-id="fdfd6-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="fdfd6-116">Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span><span class="sxs-lookup"><span data-stu-id="fdfd6-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdfd6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="fdfd6-117">See Also</span></span>  
 <xref:System.Windows.Forms.WebBrowser>  
 [<span data-ttu-id="fdfd6-118">WebBrowser (control)</span><span class="sxs-lookup"><span data-stu-id="fdfd6-118">WebBrowser Control</span></span>](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)
