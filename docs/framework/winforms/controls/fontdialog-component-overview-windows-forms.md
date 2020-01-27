---
title: Información general sobre el componente FontDialog
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 664b756dc068ca283e4f43edbdd0f3266f5d1142
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745706"
---
# <a name="fontdialog-component-overview-windows-forms"></a><span data-ttu-id="0752c-102">Información general sobre el componente FontDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="0752c-102">FontDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="0752c-103">El componente <xref:System.Windows.Forms.FontDialog> de Windows Forms es un cuadro de diálogo configurado previamente, que es el cuadro de diálogo **fuente** estándar de Windows que se usa para exponer las fuentes que están instaladas actualmente en el sistema.</span><span class="sxs-lookup"><span data-stu-id="0752c-103">The Windows Forms <xref:System.Windows.Forms.FontDialog> component is a pre-configured dialog box, which is the standard Windows **Font** dialog box used to expose the fonts that are currently installed on the system.</span></span> <span data-ttu-id="0752c-104">Úselo en su aplicación basada en Windows como una solución sencilla para la selección de fuentes en lugar de configurar su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0752c-104">Use it within your Windows-based application as a simple solution for font selection in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="0752c-105">De forma predeterminada, el cuadro de diálogo muestra los cuadros de lista de fuente, estilo de fuente y tamaño; casillas de efectos como tachado y subrayado; lista desplegable para script; y un ejemplo de cómo aparecerá la fuente.</span><span class="sxs-lookup"><span data-stu-id="0752c-105">By default, the dialog box shows list boxes for Font, Font style, and Size; check boxes for effects like Strikeout and Underline; a drop-down list for Script; and a sample of how the font will appear.</span></span> <span data-ttu-id="0752c-106">(El script hace referencia a distintos scripts de caracteres que están disponibles para una fuente determinada, por ejemplo, hebreo o japonés). Para mostrar el cuadro de diálogo fuente, llame al método <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A>.</span><span class="sxs-lookup"><span data-stu-id="0752c-106">(Script refers to different character scripts that are available for a given font, for example, Hebrew or Japanese.) To display the font dialog box, call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="0752c-107">Propiedades clave</span><span class="sxs-lookup"><span data-stu-id="0752c-107">Key Properties</span></span>  
 <span data-ttu-id="0752c-108">El componente tiene varias propiedades que configuran su apariencia.</span><span class="sxs-lookup"><span data-stu-id="0752c-108">The component has a number of properties that configure its appearance.</span></span> <span data-ttu-id="0752c-109">Las propiedades que establecen las selecciones de cuadro de diálogo son <xref:System.Windows.Forms.FontDialog.Font%2A> y <xref:System.Windows.Forms.FontDialog.Color%2A>.</span><span class="sxs-lookup"><span data-stu-id="0752c-109">The properties that set the dialog-box selections are <xref:System.Windows.Forms.FontDialog.Font%2A> and <xref:System.Windows.Forms.FontDialog.Color%2A>.</span></span> <span data-ttu-id="0752c-110">La propiedad <xref:System.Windows.Forms.FontDialog.Font%2A> establece la fuente, el estilo, el tamaño, el script y los efectos; por ejemplo, `Arial, 10pt, style=Italic, Strikeout`.</span><span class="sxs-lookup"><span data-stu-id="0752c-110">The <xref:System.Windows.Forms.FontDialog.Font%2A> property sets the font, style, size, script, and effects; for example, `Arial, 10pt, style=Italic, Strikeout`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0752c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="0752c-111">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="0752c-112">FontDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="0752c-112">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)
