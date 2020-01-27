---
title: Mostrar una fecha en un formato personalizado con el control DateTimePicker
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DateTimePicker control [Windows Forms], display styles
- examples [Windows Forms], DateTimePicker control
- dates [Windows Forms], displaying in DateTimePicker control
ms.assetid: 39767691-2d2b-46b6-a663-b7901e581a6e
ms.openlocfilehash: a27dbe737b81af86c0ac50b791bcd87bafe05b4f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745936"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="cca7b-102">Cómo: Mostrar una fecha en un formato personalizado con el control DateTimePicker de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cca7b-102">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="cca7b-103">El control Windows Forms <xref:System.Windows.Forms.DateTimePicker> le proporciona flexibilidad para dar formato a la presentación de fechas y horas en el control.</span><span class="sxs-lookup"><span data-stu-id="cca7b-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="cca7b-104">La propiedad <xref:System.Windows.Forms.DateTimePicker.Format%2A> permite seleccionar entre formatos predefinidos, que se enumeran en el <xref:System.Windows.Forms.DateTimePickerFormat>.</span><span class="sxs-lookup"><span data-stu-id="cca7b-104">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="cca7b-105">Si ninguno de ellos es adecuado para sus propósitos, puede crear su propio estilo de formato con los caracteres de formato enumerados en <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span><span class="sxs-lookup"><span data-stu-id="cca7b-105">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="cca7b-106">Para mostrar un formato personalizado</span><span class="sxs-lookup"><span data-stu-id="cca7b-106">To display a custom format</span></span>  
  
1. <span data-ttu-id="cca7b-107">Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.Format%2A> en `DateTimePickerFormat.Custom`.</span><span class="sxs-lookup"><span data-stu-id="cca7b-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2. <span data-ttu-id="cca7b-108">Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> en una cadena de formato.</span><span class="sxs-lookup"><span data-stu-id="cca7b-108">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
    ```vb  
    DateTimePicker1.Format = DateTimePickerFormat.Custom  
    ' Display the date as "Mon 27 Feb 2012".  
    DateTimePicker1.CustomFormat = "ddd dd MMM yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.Format = DateTimePickerFormat.Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1.CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->Format = DateTimePickerFormat::Custom;  
    // Display the date as "Mon 27 Feb 2012".  
    dateTimePicker1->CustomFormat = "ddd dd MMM yyyy";  
    ```  
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="cca7b-109">Para agregar texto al valor con formato</span><span class="sxs-lookup"><span data-stu-id="cca7b-109">To add text to the formatted value</span></span>  
  
1. <span data-ttu-id="cca7b-110">Use comillas simples para encerrar cualquier carácter que no sea un carácter de formato como "M" o un delimitador como ":".</span><span class="sxs-lookup"><span data-stu-id="cca7b-110">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="cca7b-111">Por ejemplo, la cadena de formato siguiente muestra la fecha actual con el formato "hoy es: 05:30:31 Friday marzo 02, 2012" en la referencia cultural inglés (Estados Unidos).</span><span class="sxs-lookup"><span data-stu-id="cca7b-111">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
    ```vb  
    DateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy"  
    ```  
  
    ```csharp  
    dateTimePicker1.CustomFormat = "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
    ```cpp  
    dateTimePicker1->CustomFormat =  
       "'Today is:' hh:mm:ss dddd MMMM dd, yyyy";  
    ```  
  
     <span data-ttu-id="cca7b-112">En función de la configuración de la referencia cultural, se pueden cambiar los caracteres no incluidos entre comillas simples.</span><span class="sxs-lookup"><span data-stu-id="cca7b-112">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="cca7b-113">Por ejemplo, la cadena de formato anterior muestra la fecha actual con el formato "hoy es: 05:30:31 Friday marzo 02, 2012" en la referencia cultural inglés (Estados Unidos).</span><span class="sxs-lookup"><span data-stu-id="cca7b-113">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="cca7b-114">Tenga en cuenta que los primeros dos puntos están entre comillas simples, ya que no pretende ser un carácter delimitador, como en "HH: mm: SS".</span><span class="sxs-lookup"><span data-stu-id="cca7b-114">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="cca7b-115">En otra referencia cultural, el formato puede aparecer como "hoy es: 05.30.31 Friday marzo 02, 2012".</span><span class="sxs-lookup"><span data-stu-id="cca7b-115">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cca7b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="cca7b-116">See also</span></span>

- [<span data-ttu-id="cca7b-117">Control DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="cca7b-117">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="cca7b-118">Establecer y devolver fechas con el control DateTimePicker de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cca7b-118">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
