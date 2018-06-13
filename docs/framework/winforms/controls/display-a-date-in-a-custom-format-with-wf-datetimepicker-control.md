---
title: 'Cómo: Mostrar una fecha en un formato personalizado con el control DateTimePicker de formularios Windows Forms'
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
ms.openlocfilehash: 2f563b5de9b80dab2af00290e8a6b3b309410a9e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526014"
---
# <a name="how-to-display-a-date-in-a-custom-format-with-the-windows-forms-datetimepicker-control"></a><span data-ttu-id="470c7-102">Cómo: Mostrar una fecha en un formato personalizado con el control DateTimePicker de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="470c7-102">How to: Display a Date in a Custom Format with the Windows Forms DateTimePicker Control</span></span>
<span data-ttu-id="470c7-103">Los formularios Windows Forms <xref:System.Windows.Forms.DateTimePicker> control ofrece flexibilidad para dar formato a la presentación de fechas y horas en el control.</span><span class="sxs-lookup"><span data-stu-id="470c7-103">The Windows Forms <xref:System.Windows.Forms.DateTimePicker> control gives you flexibility in formatting the display of dates and times in the control.</span></span> <span data-ttu-id="470c7-104">El <xref:System.Windows.Forms.DateTimePicker.Format%2A> propiedad le permite seleccionar entre los formatos predefinidos, aparecen en la <xref:System.Windows.Forms.DateTimePickerFormat>.</span><span class="sxs-lookup"><span data-stu-id="470c7-104">The <xref:System.Windows.Forms.DateTimePicker.Format%2A> property allows you to select from predefined formats, listed in the <xref:System.Windows.Forms.DateTimePickerFormat>.</span></span> <span data-ttu-id="470c7-105">Si ninguno de estos es adecuado para sus necesidades, puede crear su propio estilo de formato de caracteres de formato que se indican en <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span><span class="sxs-lookup"><span data-stu-id="470c7-105">If none of these is adequate for your purposes, you can create your own format style using format characters listed in <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A>.</span></span>  
  
### <a name="to-display-a-custom-format"></a><span data-ttu-id="470c7-106">Para mostrar un formato personalizado</span><span class="sxs-lookup"><span data-stu-id="470c7-106">To display a custom format</span></span>  
  
1.  <span data-ttu-id="470c7-107">Establezca la propiedad <xref:System.Windows.Forms.DateTimePicker.Format%2A> en `DateTimePickerFormat.Custom`.</span><span class="sxs-lookup"><span data-stu-id="470c7-107">Set the <xref:System.Windows.Forms.DateTimePicker.Format%2A> property to `DateTimePickerFormat.Custom`.</span></span>  
  
2.  <span data-ttu-id="470c7-108">Establecer el <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> propiedad a una cadena de formato.</span><span class="sxs-lookup"><span data-stu-id="470c7-108">Set the <xref:System.Windows.Forms.DateTimePicker.CustomFormat%2A> property to a format string.</span></span>  
  
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
  
### <a name="to-add-text-to-the-formatted-value"></a><span data-ttu-id="470c7-109">Para agregar texto al valor con formato</span><span class="sxs-lookup"><span data-stu-id="470c7-109">To add text to the formatted value</span></span>  
  
1.  <span data-ttu-id="470c7-110">Utilice comillas simples para delimitar cualquier carácter que no es un carácter de formato como "M" o un delimitador como ":".</span><span class="sxs-lookup"><span data-stu-id="470c7-110">Use single quotation marks to enclose any character that is not a format character like "M" or a delimiter like ":".</span></span> <span data-ttu-id="470c7-111">Por ejemplo, la siguiente cadena de formato muestra la fecha actual con el formato "en la actualidad es: 05:30:31 el viernes 02 de marzo de 2012" en el inglés (Estados Unidos) de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="470c7-111">For example, the format string below displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span>  
  
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
  
     <span data-ttu-id="470c7-112">Según la configuración de la referencia cultural, se puede cambiar cualquier carácter no encerrado entre comillas simples.</span><span class="sxs-lookup"><span data-stu-id="470c7-112">Depending on the culture setting, any characters not enclosed in single quotation marks may be changed.</span></span> <span data-ttu-id="470c7-113">Por ejemplo, la cadena de formato anterior muestra la fecha actual con el formato "en la actualidad es: 05:30:31 el viernes 02 de marzo de 2012" en el inglés (Estados Unidos) de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="470c7-113">For example, the format string above displays the current date with the format "Today is: 05:30:31 Friday March 02, 2012" in the English (United States) culture.</span></span> <span data-ttu-id="470c7-114">Tenga en cuenta que los primeros dos puntos están encerrados entre comillas simples, porque no está pensado para ser un carácter delimitador como en "hh".</span><span class="sxs-lookup"><span data-stu-id="470c7-114">Note that the first colon is enclosed in single quotation marks, because it is not intended to be a delimiting character as it is in "hh:mm:ss".</span></span> <span data-ttu-id="470c7-115">En otra referencia cultural, el formato puede aparecer como "en la actualidad es: 05.30.31 el viernes 02 de marzo de 2012".</span><span class="sxs-lookup"><span data-stu-id="470c7-115">In another culture, the format might appear as "Today is: 05.30.31 Friday March 02, 2012".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="470c7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="470c7-116">See Also</span></span>  
 [<span data-ttu-id="470c7-117">Control DateTimePicker</span><span class="sxs-lookup"><span data-stu-id="470c7-117">DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)  
 [<span data-ttu-id="470c7-118">Establecer y devolver fechas con el control DateTimePicker de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="470c7-118">How to: Set and Return Dates with the Windows Forms DateTimePicker Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-and-return-dates-with-the-windows-forms-datetimepicker-control.md)
