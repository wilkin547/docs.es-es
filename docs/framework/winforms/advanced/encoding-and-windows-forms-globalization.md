---
title: Codificación y globalización de Windows Forms
ms.date: 03/30/2017
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
ms.openlocfilehash: 60ca9f7ba2f716b5dab1b0276bc3cd07ddd8f65c
ms.sourcegitcommit: 878ca7550b653114c3968ef8906da2b3e60e3c7a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2019
ms.locfileid: "71736885"
---
# <a name="encoding-and-windows-forms-globalization"></a><span data-ttu-id="ebf14-102">Codificación y globalización de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ebf14-102">Encoding and Windows Forms Globalization</span></span>

<span data-ttu-id="ebf14-103">Las aplicaciones de Windows Forms están totalmente habilitadas para Unicode, lo que significa que cada carácter se representa mediante un número único, independientemente de la plataforma, el programa o el idioma.</span><span class="sxs-lookup"><span data-stu-id="ebf14-103">Windows Forms applications are entirely Unicode-enabled, meaning that each character is represented by a unique number, no matter what the platform, program, or language.</span></span> <span data-ttu-id="ebf14-104">Para obtener más información sobre Unicode, vea el [sitio web de Unicode Consortium](https://www.unicode.org).</span><span class="sxs-lookup"><span data-stu-id="ebf14-104">For more information about Unicode, see the [Unicode consortium Web site](https://www.unicode.org).</span></span>

## <a name="benefits-of-unicode"></a><span data-ttu-id="ebf14-105">Ventajas de Unicode</span><span class="sxs-lookup"><span data-stu-id="ebf14-105">Benefits of Unicode</span></span>

<span data-ttu-id="ebf14-106">Entre las ventajas de los formularios habilitados para Unicode se incluye la capacidad de trabajar con scripts que son solo Unicode, como el Hindi.</span><span class="sxs-lookup"><span data-stu-id="ebf14-106">The benefits of Unicode-enabled forms include the ability to work with scripts that are Unicode-only, such as Hindi.</span></span> <span data-ttu-id="ebf14-107">Además, puede usar varios idiomas en un único formulario.</span><span class="sxs-lookup"><span data-stu-id="ebf14-107">In addition, you can use multiple languages on a single form.</span></span> <span data-ttu-id="ebf14-108">En Unicode, todos los caracteres tienen una longitud de dos bytes, por lo que no es necesario realizar ningún esfuerzo especial para representar los caracteres de doble byte.</span><span class="sxs-lookup"><span data-stu-id="ebf14-108">In Unicode, all characters are two bytes long, so no special effort is needed to represent double-byte characters.</span></span> <span data-ttu-id="ebf14-109">También puede escribir un único conjunto de código que funcionará en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="ebf14-109">You can also write a single set of code that will work on all platforms.</span></span> <span data-ttu-id="ebf14-110">Se trata de un cambio respecto a las versiones anteriores de Visual Basic, en el que tenía que escribir código diferente para distintas plataformas, como Windows NT y Windows 98.</span><span class="sxs-lookup"><span data-stu-id="ebf14-110">This is a change from previous versions of Visual Basic, in which you had to write different code for different platforms, such as Windows NT and Windows 98.</span></span>

<span data-ttu-id="ebf14-111">Sin embargo, ciertos controles no admiten Unicode en Windows 98 y Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="ebf14-111">However, certain controls do not support Unicode in Windows 98 and Windows Millennium Edition.</span></span> <span data-ttu-id="ebf14-112">Estos controles, que heredan del control común, procesarán los datos con las páginas de códigos de Windows como ANSI.</span><span class="sxs-lookup"><span data-stu-id="ebf14-112">These controls, all of which inherit from the common control, will process data with the Windows code pages, as ANSI.</span></span> <span data-ttu-id="ebf14-113">Estos controles son: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar> y <xref:System.Windows.Forms.StatusBar>.</span><span class="sxs-lookup"><span data-stu-id="ebf14-113">These controls are: <xref:System.Windows.Forms.TabControl>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.DateTimePicker>, <xref:System.Windows.Forms.MonthCalendar>, <xref:System.Windows.Forms.TrackBar>, <xref:System.Windows.Forms.ProgressBar>, <xref:System.Windows.Forms.ImageList>, <xref:System.Windows.Forms.ToolBar>, and <xref:System.Windows.Forms.StatusBar>.</span></span> <span data-ttu-id="ebf14-114">Como resultado, no puede mostrar datos Unicode en estos controles en las plataformas indicadas.</span><span class="sxs-lookup"><span data-stu-id="ebf14-114">As a result, you cannot display Unicode data in these controls on the listed platforms.</span></span> <span data-ttu-id="ebf14-115">Por ejemplo, no puede mostrar caracteres japoneses en un sistema operativo Windows 98 en inglés.</span><span class="sxs-lookup"><span data-stu-id="ebf14-115">For example, you cannot display Japanese characters on an English Windows 98 operating system.</span></span>

<span data-ttu-id="ebf14-116">Para obtener alternativas con reconocimiento de Unicode a los controles <xref:System.Windows.Forms.ToolBar> y <xref:System.Windows.Forms.StatusBar>, use los controles <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.StatusStrip>, que sustituyen a los controles más antiguos.</span><span class="sxs-lookup"><span data-stu-id="ebf14-116">For Unicode-aware alternatives to the <xref:System.Windows.Forms.ToolBar> and <xref:System.Windows.Forms.StatusBar> controls, use the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.StatusStrip> controls, which replace these older controls.</span></span> <span data-ttu-id="ebf14-117">Para mantener una apariencia similar entre los elementos visuales de la aplicación, use el control <xref:System.Windows.Forms.MenuStrip> para representar menús en lugar de <xref:System.Windows.Forms.MainMenu>.</span><span class="sxs-lookup"><span data-stu-id="ebf14-117">To maintain a similar look and feel between visual elements in your application, use the <xref:System.Windows.Forms.MenuStrip> control for rendering menus instead of <xref:System.Windows.Forms.MainMenu>.</span></span> <span data-ttu-id="ebf14-118">Igual que <xref:System.Windows.Forms.ToolStrip> y <xref:System.Windows.Forms.StatusStrip>, <xref:System.Windows.Forms.MenuStrip> también puede procesar y mostrar caracteres Unicode.</span><span class="sxs-lookup"><span data-stu-id="ebf14-118">Like <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.StatusStrip>, <xref:System.Windows.Forms.MenuStrip> can also process and display Unicode characters.</span></span>

## <a name="see-also"></a><span data-ttu-id="ebf14-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebf14-119">See also</span></span>

- [<span data-ttu-id="ebf14-120">Globalizar aplicaciones Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ebf14-120">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)
