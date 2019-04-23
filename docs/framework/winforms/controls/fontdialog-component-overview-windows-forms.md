---
title: Información general sobre el componente FontDialog (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- FontDialog
helpviewer_keywords:
- Font dialog box [Windows Forms], Windows Forms
- Font dialog box
- FontDialog component [Windows Forms], about FontDialog component
ms.assetid: daf46e57-1b4b-4b7a-bad0-b50ca7ba75dc
ms.openlocfilehash: 7f140807bf4b42e530302190042e729c59248e7f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59098564"
---
# <a name="fontdialog-component-overview-windows-forms"></a><span data-ttu-id="1e262-102">Información general sobre el componente FontDialog (formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="1e262-102">FontDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="1e262-103">Los formularios de Windows <xref:System.Windows.Forms.FontDialog> componente es un cuadro de diálogo preconfigurado, que es el estándar Windows **fuente** cuadro de diálogo que se utiliza para exponer las fuentes que están instaladas actualmente en el sistema.</span><span class="sxs-lookup"><span data-stu-id="1e262-103">The Windows Forms <xref:System.Windows.Forms.FontDialog> component is a pre-configured dialog box, which is the standard Windows **Font** dialog box used to expose the fonts that are currently installed on the system.</span></span> <span data-ttu-id="1e262-104">Utilícelo dentro de la aplicación basada en Windows como una solución sencilla para la selección de fuente en lugar de configurar su propio cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="1e262-104">Use it within your Windows-based application as a simple solution for font selection in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="1e262-105">De forma predeterminada, el cuadro de diálogo muestra cuadros de lista para la fuente, estilo de fuente y tamaño; casillas de verificación para los efectos como tachado y subrayado; una lista desplegable para la secuencia de comandos. y un ejemplo de cómo aparecerá la fuente.</span><span class="sxs-lookup"><span data-stu-id="1e262-105">By default, the dialog box shows list boxes for Font, Font style, and Size; check boxes for effects like Strikeout and Underline; a drop-down list for Script; and a sample of how the font will appear.</span></span> <span data-ttu-id="1e262-106">(Secuencia de comandos hace referencia a scripts de distintos juegos de caracteres que están disponibles para una fuente determinada, por ejemplo, hebreo o japonés.) Para mostrar el cuadro de diálogo fuente, llame a la <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> método.</span><span class="sxs-lookup"><span data-stu-id="1e262-106">(Script refers to different character scripts that are available for a given font, for example, Hebrew or Japanese.) To display the font dialog box, call the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="1e262-107">Propiedades clave</span><span class="sxs-lookup"><span data-stu-id="1e262-107">Key Properties</span></span>  
 <span data-ttu-id="1e262-108">El componente tiene un número de propiedades que configuran su apariencia.</span><span class="sxs-lookup"><span data-stu-id="1e262-108">The component has a number of properties that configure its appearance.</span></span> <span data-ttu-id="1e262-109">Las propiedades que establecen las selecciones de cuadro de diálogo son <xref:System.Windows.Forms.FontDialog.Font%2A> y <xref:System.Windows.Forms.FontDialog.Color%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e262-109">The properties that set the dialog-box selections are <xref:System.Windows.Forms.FontDialog.Font%2A> and <xref:System.Windows.Forms.FontDialog.Color%2A>.</span></span> <span data-ttu-id="1e262-110">El <xref:System.Windows.Forms.FontDialog.Font%2A> propiedad establece la fuente, estilo, tamaño, script y efectos; por ejemplo, `Arial, 10pt, style=Italic, Strikeout`.</span><span class="sxs-lookup"><span data-stu-id="1e262-110">The <xref:System.Windows.Forms.FontDialog.Font%2A> property sets the font, style, size, script, and effects; for example, `Arial, 10pt, style=Italic, Strikeout`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e262-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e262-111">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="1e262-112">FontDialog (componente)</span><span class="sxs-lookup"><span data-stu-id="1e262-112">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)
