---
title: Procedimiento para mostrar una fecha en un formato personalizado con el control DateTimePicker de formularios Windows Forms
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
ms.openlocfilehash: 08d5a505229cd434dbf82e8ae4624bb418efd379
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59335945"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="6f06a-102">Procedimiento para mostrar una fecha en un formato personalizado con el control DateTimePicker de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="6f06a-102">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="6f06a-103">Los formularios de Windows <xref:System.Windows.Forms.DateTimePicker> control ofrece flexibilidad para dar formato a la presentación de fechas y horas en el control.</span><span class="sxs-lookup"><span data-stu-id="6f06a-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="6f06a-104">El <xref:System.Windows.Forms.DateTimePicker.Format%2A> propiedad le permite seleccionar de los formatos predefinidos enumerados en el <xref:System.Windows.Forms.DateTimePickerFormat>.</span><span class="sxs-lookup"><span data-stu-id="6f06a-104">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="6f06a-105">Si ninguno de estos es adecuado para sus fines, puede crear su propio estilo de formato de caracteres de formato enumerados en <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span><span class="sxs-lookup"><span data-stu-id="6f06a-105">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="6f06a-106">Para mostrar un formato personalizado</span><span class="sxs-lookup"><span data-stu-id="6f06a-106">To display a custom format</span></span>  
  
1. <span data-ttu-id="6f06a-107">Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.Format%2A> en `DateTimePickerFormat.Custom`.</span><span class="sxs-lookup"><span data-stu-id="6f06a-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2. <span data-ttu-id="6f06a-108">Establecer el <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> propiedad a una cadena de formato.</span><span class="sxs-lookup"><span data-stu-id="6f06a-108">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="6f06a-109">Para agregar texto al valor con formato</span><span class="sxs-lookup"><span data-stu-id="6f06a-109">To add text to the formatted value</span></span>  
  
1. <span data-ttu-id="6f06a-110">Utilice comillas simples para incluir cualquier carácter que no sea un carácter de formato como "M" o un delimitador como ":".</span><span class="sxs-lookup"><span data-stu-id="6f06a-110">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="6f06a-111">Por ejemplo, la siguiente cadena de formato muestra la fecha actual con el formato "hoy en día es: 05:30:31 Friday March 02, 2012" en la referencia cultural inglés (Estados Unidos).</span><span class="sxs-lookup"><span data-stu-id="6f06a-111">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
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
  
     <span data-ttu-id="6f06a-112">Según la configuración de la referencia cultural, se puede cambiar cualquier carácter que no se incluyen entre comillas simples.</span><span class="sxs-lookup"><span data-stu-id="6f06a-112">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="6f06a-113">Por ejemplo, la cadena de formato anterior muestra la fecha actual con el formato "hoy en día es: 05:30:31 Friday March 02, 2012" en la referencia cultural inglés (Estados Unidos).</span><span class="sxs-lookup"><span data-stu-id="6f06a-113">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="6f06a-114">Tenga en cuenta que los primeros dos puntos se incluye entre comillas simples, porque no está diseñado para ser un carácter delimitador cuando sea "hh".</span><span class="sxs-lookup"><span data-stu-id="6f06a-114">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="6f06a-115">En otra referencia cultural, el formato puede aparecer como "hoy en día es: 05.30.31 el viernes marzo 02, 2012".</span><span class="sxs-lookup"><span data-stu-id="6f06a-115">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f06a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f06a-116">See also</span></span>

- [<span data-ttu-id="6f06a-117">Control DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="6f06a-117">DateTimePicker Control</span></span>](datetimepicker-control-windows-forms.md)
- [<span data-ttu-id="6f06a-118">Cómo: Establecer y devolver fechas con el Control DateTimePicker de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="6f06a-118">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
