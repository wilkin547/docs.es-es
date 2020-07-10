---
title: Agregar funcionalidades del explorador Web a la aplicación
description: Aprenda a agregar funcionalidades del explorador Web a una aplicación Windows Forms con el control WebBrowser.
ms.date: 03/30/2017
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
ms.openlocfilehash: a5a33961ac8301bda86bb5f34e65ac159308987f
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174554"
---
# <a name="how-to-add-web-browser-capabilities-to-a-windows-forms-application"></a><span data-ttu-id="9c8d0-103">Cómo agregar funcionalidades del explorador Web a una aplicación Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9c8d0-103">How to add web browser capabilities to a Windows Forms application</span></span>

<span data-ttu-id="9c8d0-104">Con el control <xref:System.Windows.Forms.WebBrowser>, puede agregar funcionalidades del explorador web a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9c8d0-104">With the <xref:System.Windows.Forms.WebBrowser> control, you can add Web browser functionality to your application.</span></span> <span data-ttu-id="9c8d0-105">De forma predeterminada, el control funciona como un explorador web.</span><span class="sxs-lookup"><span data-stu-id="9c8d0-105">The control works like a Web browser by default.</span></span> <span data-ttu-id="9c8d0-106">Después de cargar una dirección URL inicial estableciendo la propiedad <xref:System.Windows.Forms.WebBrowser.Url%2A>, puede navegar haciendo clic en hipervínculos o utilizando métodos abreviados de teclado para avanzar y retroceder por el historial de navegación.</span><span class="sxs-lookup"><span data-stu-id="9c8d0-106">After you load an initial URL by setting the <xref:System.Windows.Forms.WebBrowser.Url%2A> property, you can navigate by clicking hyperlinks or by using keyboard shortcuts to move backward and forward through navigation history.</span></span> <span data-ttu-id="9c8d0-107">De forma predeterminada, puede acceder a funcionalidades adicionales del explorador a través del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="9c8d0-107">By default, you can access additional browser functionality through the right-click shortcut menu.</span></span> <span data-ttu-id="9c8d0-108">También puede abrir documentos nuevos colocándolos en el control.</span><span class="sxs-lookup"><span data-stu-id="9c8d0-108">You can also open new documents by dropping them onto the control.</span></span> <span data-ttu-id="9c8d0-109">El control <xref:System.Windows.Forms.WebBrowser> también tiene varias propiedades, métodos y eventos que puede utilizar para implementar características de interfaz de usuario similares a las que se encuentran en Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="9c8d0-109">The <xref:System.Windows.Forms.WebBrowser> control also has several properties, methods, and events that you can use to implement user interface features similar to those found in Internet Explorer.</span></span>

<span data-ttu-id="9c8d0-110">En el ejemplo de código siguiente, se implementa una barra de direcciones, los botones de exploración típicos, un menú **Archivo**, una barra de estado y una barra de título que muestra el título de la página actual.</span><span class="sxs-lookup"><span data-stu-id="9c8d0-110">The following code example implements an address bar, typical browser buttons, a **File** menu, a status bar, and a title bar that displays the current page title.</span></span>

## <a name="example"></a><span data-ttu-id="9c8d0-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9c8d0-111">Example</span></span>

[!code-cpp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CPP/form1.cpp#0)]
[!code-csharp[System.Windows.Forms.WebBrowser#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.WebBrowser#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/VB/form1.vb#0)]
  
## <a name="compile-the-code"></a><span data-ttu-id="9c8d0-112">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="9c8d0-112">Compile the code</span></span>

<span data-ttu-id="9c8d0-113">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="9c8d0-113">This example requires:</span></span>

- <span data-ttu-id="9c8d0-114">Referencias a los ensamblados `System`, `System.Drawing` y `System.Windows.Forms`.</span><span class="sxs-lookup"><span data-stu-id="9c8d0-114">References to the `System`, `System.Drawing`, and `System.Windows.Forms` assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="9c8d0-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c8d0-115">See also</span></span>

- <xref:System.Windows.Forms.WebBrowser>
- [<span data-ttu-id="9c8d0-116">WebBrowser (Control)</span><span class="sxs-lookup"><span data-stu-id="9c8d0-116">WebBrowser Control</span></span>](webbrowser-control-windows-forms.md)
