---
title: Visualización de caracteres asiáticos con la propiedad ImeMode
ms.date: 03/30/2017
helpviewer_keywords:
- Asian languages [Windows Forms], displaying with ImeMode
- Chinese characters [Windows Forms], displaying with ImeMode
- IME mode
- Japanese characters [Windows Forms], displaying with ImeMode
- international applications [Windows Forms], character display
- international characters
- Korean characters
- Asian languages
- Input Method Editor (IME), mode
- localization [Windows Forms], character sets
- globalization [Windows Forms], character sets
ms.assetid: c60ae399-0dab-4f07-9dea-6dbfb15ec0ae
ms.openlocfilehash: d3733f642d4218c851040582ee5637b5486a7804
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36208633"
---
# <a name="display-of-asian-characters-with-the-imemode-property"></a><span data-ttu-id="8b287-102">Visualización de caracteres asiáticos con la propiedad ImeMode</span><span class="sxs-lookup"><span data-stu-id="8b287-102">Display of Asian Characters with the ImeMode Property</span></span>
<span data-ttu-id="8b287-103">El <xref:System.Windows.Forms.Control.ImeMode%2A> propiedad se usa en los formularios y controles para imponer un modo determinado a un editor de métodos de entrada (IME).</span><span class="sxs-lookup"><span data-stu-id="8b287-103">The <xref:System.Windows.Forms.Control.ImeMode%2A> property is used by forms and controls to force a specific mode for an input method editor (IME).</span></span> <span data-ttu-id="8b287-104">El IME es un componente esencial para escribir scripts en chino, japonés y coreano, ya que estos sistemas de escritura tienen más caracteres que pueden codificarse para un teclado normal.</span><span class="sxs-lookup"><span data-stu-id="8b287-104">The IME is an essential component for writing Chinese, Japanese, and Korean scripts, since these writing systems have more characters than can be encoded for a regular keyboard.</span></span> <span data-ttu-id="8b287-105">Por ejemplo, puede que solo quiera permitir caracteres ASCII en un cuadro de texto determinado.</span><span class="sxs-lookup"><span data-stu-id="8b287-105">For example, you may want to allow only ASCII characters in a particular text box.</span></span> <span data-ttu-id="8b287-106">En tal caso puede establecer la <xref:System.Windows.Forms.Control.ImeMode%2A> propiedad <xref:System.Windows.Forms.ImeMode> y los usuarios sólo podrán escribir caracteres ASCII para ese cuadro de texto determinado.</span><span class="sxs-lookup"><span data-stu-id="8b287-106">In such a case you can set the <xref:System.Windows.Forms.Control.ImeMode%2A> property to <xref:System.Windows.Forms.ImeMode> and users will only be able to enter ASCII characters for that particular text box.</span></span> <span data-ttu-id="8b287-107">El valor predeterminado de la <xref:System.Windows.Forms.Control.ImeMode%2A> propiedad es <xref:System.Windows.Forms.ImeMode>, por lo que si establece la propiedad de un formulario, todos los controles del formulario heredarán esa configuración.</span><span class="sxs-lookup"><span data-stu-id="8b287-107">The default value of the <xref:System.Windows.Forms.Control.ImeMode%2A> property is <xref:System.Windows.Forms.ImeMode>, so if you set the property for a form, all controls on the form will inherit that setting.</span></span> <span data-ttu-id="8b287-108">Para obtener más información, consulte <xref:System.Windows.Forms.Control.ImeMode%2A> ) y <xref:System.Windows.Forms.ImeMode>.</span><span class="sxs-lookup"><span data-stu-id="8b287-108">For more information, see <xref:System.Windows.Forms.Control.ImeMode%2A> ) and <xref:System.Windows.Forms.ImeMode>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b287-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b287-109">See also</span></span>

[<span data-ttu-id="8b287-110">Globalizar aplicaciones de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="8b287-110">Globalizing Windows Forms applications</span></span>](globalizing-windows-forms.md)
