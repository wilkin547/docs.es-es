---
title: "Codificación y globalización de Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ListView control [Windows Forms], lack of Unicode support
- DateTimePicker control [Windows Forms], lack of Unicode support
- TrackBar control [Windows Forms], lack of Unicode support
- ImageList component [Windows Forms], lack of Unicode support
- Unicode [Windows Forms]
- ToolBar control [Windows Forms], lack of Unicode support
- international applications [Windows Forms], character display
- StatusBar control [Windows Forms], lack of Unicode support
- MonthCalendar control [Windows Forms], lack of Unicode support
- international characters
- TabControl control [Windows Forms], lack of Unicode support
- Windows Forms, encoding
- TreeView control [Windows Forms], lack of Unicode support
- ProgressBar control [Windows Forms], Unicode-enabled forms
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: 22e8965d-a712-42b3-8167-3ee346bd70f9
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cbac07e92d892913f2d2a342b2fa5b3d5fe2f40c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="encoding-and-windows-forms-globalization"></a><span data-ttu-id="9b035-102">Codificación y globalización de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9b035-102">Encoding and Windows Forms Globalization</span></span>
<span data-ttu-id="9b035-103">Las aplicaciones de Windows Forms están totalmente habilitadas para Unicode, lo que significa que cada carácter se representa mediante un número único, independientemente de la plataforma, el programa o el idioma.</span><span class="sxs-lookup"><span data-stu-id="9b035-103">Windows Forms applications are entirely Unicode-enabled, meaning that each character is represented by a unique number, no matter what the platform, program, or language.</span></span> <span data-ttu-id="9b035-104">Para obtener más información sobre Unicode, vea el [sitio Web de Unicode consortium](http://www.unicode.org).</span><span class="sxs-lookup"><span data-stu-id="9b035-104">For more information about Unicode, see the [Unicode consortium Web site](http://www.unicode.org).</span></span>  
  
## <a name="benefits-of-unicode"></a><span data-ttu-id="9b035-105">Ventajas de Unicode</span><span class="sxs-lookup"><span data-stu-id="9b035-105">Benefits of Unicode</span></span>  
 <span data-ttu-id="9b035-106">Entre las ventajas de los formularios habilitados para Unicode se incluye la capacidad de trabajar con scripts que son solo Unicode, como el Hindi.</span><span class="sxs-lookup"><span data-stu-id="9b035-106">The benefits of Unicode-enabled forms include the ability to work with scripts that are Unicode-only, such as Hindi.</span></span> <span data-ttu-id="9b035-107">Además, puede usar varios idiomas en un único formulario.</span><span class="sxs-lookup"><span data-stu-id="9b035-107">In addition, you can use multiple languages on a single form.</span></span> <span data-ttu-id="9b035-108">En Unicode, todos los caracteres tienen una longitud de dos bytes, por lo que no es necesario realizar ningún esfuerzo especial para representar los caracteres de doble byte.</span><span class="sxs-lookup"><span data-stu-id="9b035-108">In Unicode, all characters are two bytes long, so no special effort is needed to represent double-byte characters.</span></span> <span data-ttu-id="9b035-109">También puede escribir un único conjunto de código que funcionará en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="9b035-109">You can also write a single set of code that will work on all platforms.</span></span> <span data-ttu-id="9b035-110">Se trata de un cambio respecto a versiones anteriores de [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], en las que tenía que escribir código diferente para distintas plataformas, como Windows NT y [!INCLUDE[win98](../../../../includes/win98-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b035-110">This is a change from previous versions of [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)], in which you had to write different code for different platforms, such as Windows NT and [!INCLUDE[win98](../../../../includes/win98-md.md)].</span></span>  
  
 <span data-ttu-id="9b035-111">Sin embargo, ciertos controles no admiten Unicode en [!INCLUDE[win98](../../../../includes/win98-md.md)] y Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="9b035-111">However, certain controls do not support Unicode in [!INCLUDE[win98](../../../../includes/win98-md.md)] and Windows Millennium Edition.</span></span> <span data-ttu-id="9b035-112">Estos controles, que heredan todos del control común, procesarán los datos con las páginas de códigos de Windows, como [!INCLUDE[vcpransi](../../../../includes/vcpransi-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9b035-112">These controls, all of which inherit from the common control, will process data with the Windows code pages, as [!INCLUDE[vcpransi](../../../../includes/vcpransi-md.md)].</span></span> <span data-ttu-id="9b035-113">Estos controles son: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar> y <xref:System.Windows.Forms.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="9b035-113">These controls are: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar>, and <xref:System.Windows.Forms.StatusBar>.</span></span> <span data-ttu-id="9b035-114">Como resultado, no puede mostrar datos Unicode en estos controles en las plataformas indicadas.</span><span class="sxs-lookup"><span data-stu-id="9b035-114">As a result, you cannot display Unicode data in these controls on the listed platforms.</span></span> <span data-ttu-id="9b035-115">Por ejemplo, no puede mostrar caracteres japoneses en un sistema operativo [!INCLUDE[win98](../../../../includes/win98-md.md)] en inglés.</span><span class="sxs-lookup"><span data-stu-id="9b035-115">For example, you cannot display Japanese characters on an English [!INCLUDE[win98](../../../../includes/win98-md.md)] operating system.</span></span>  
  
 <span data-ttu-id="9b035-116">Para obtener alternativas con reconocimiento de Unicode a los controles <xref:System.Windows.Forms.ToolBar> y <xref:System.Windows.Forms.StatusBar>, use los controles <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.StatusStrip>, que sustituyen a los controles más antiguos.</span><span class="sxs-lookup"><span data-stu-id="9b035-116">For Unicode-aware alternatives to the <xref:System.Windows.Forms.ToolBar> and <xref:System.Windows.Forms.StatusBar> controls, use the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.StatusStrip> controls, which replace these older controls.</span></span> <span data-ttu-id="9b035-117">Para mantener una apariencia similar entre los elementos visuales de la aplicación, use el control <xref:System.Windows.Forms.MenuStrip> para representar menús en lugar de <xref:System.Windows.Forms.MainMenu>.</span><span class="sxs-lookup"><span data-stu-id="9b035-117">To maintain a similar look and feel between visual elements in your application, use the <xref:System.Windows.Forms.MenuStrip> control for rendering menus instead of <xref:System.Windows.Forms.MainMenu>.</span></span> <span data-ttu-id="9b035-118">Igual que <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.StatusStrip>, <xref:System.Windows.Forms.MenuStrip> también puede procesar y mostrar caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="9b035-118">Like <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.StatusStrip>, <xref:System.Windows.Forms.MenuStrip> can also process and display Unicode characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b035-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b035-119">See Also</span></span>  
 [<span data-ttu-id="9b035-120">Globalizar Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9b035-120">Globalizing Windows Forms</span></span>](../../../../docs/framework/winforms/advanced/globalizing-windows-forms.md)
