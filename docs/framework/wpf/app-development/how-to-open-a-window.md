---
title: Procedimiento Abrir una ventana
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows [WPF], opening
- opening windows [WPF]
ms.assetid: 6b91b2bb-fda7-491d-a72e-139dd630a5b0
ms.openlocfilehash: 9ce7ffb3f46dd869fda7893745b531bd02d18ee1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947685"
---
# <a name="how-to-open-a-window"></a><span data-ttu-id="3cef4-102">Procedimiento Abrir una ventana</span><span class="sxs-lookup"><span data-stu-id="3cef4-102">How to: Open a Window</span></span>
<span data-ttu-id="3cef4-103">En este ejemplo se muestra cómo abrir una ventana.</span><span class="sxs-lookup"><span data-stu-id="3cef4-103">This example shows how to open a window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cef4-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3cef4-104">Example</span></span>  
 <span data-ttu-id="3cef4-105">Se abre una ventana de creación de instancias de <xref:System.Windows.Window> y llamar a la <xref:System.Windows.Window.Show%2A> método.</span><span class="sxs-lookup"><span data-stu-id="3cef4-105">A window is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.Show%2A> method.</span></span> <span data-ttu-id="3cef4-106"><xref:System.Windows.Window.Show%2A> Abre una ventana y devuelve inmediatamente sin esperar a la nueva ventana Cerrar.</span><span class="sxs-lookup"><span data-stu-id="3cef4-106"><xref:System.Windows.Window.Show%2A> opens a window and returns immediately without waiting for the new window to close.</span></span> <span data-ttu-id="3cef4-107">Este tipo de ventana también es conocido como un *no modal* ventana y no restringe la entrada del usuario.</span><span class="sxs-lookup"><span data-stu-id="3cef4-107">This type of window is also known as a *modeless* window, and doesn't restrict user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="3cef4-108">Seguridad de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="3cef4-108">.NET Framework Security</span></span>  
 <span data-ttu-id="3cef4-109">Creación de instancias <xref:System.Windows.Window> requiere permiso para llamar a métodos nativos no seguros (vea <xref:System.Windows.Window.%23ctor%2A>).</span><span class="sxs-lookup"><span data-stu-id="3cef4-109">Instantiating <xref:System.Windows.Window> requires permission to call unsafe native methods (see <xref:System.Windows.Window.%23ctor%2A>).</span></span>
