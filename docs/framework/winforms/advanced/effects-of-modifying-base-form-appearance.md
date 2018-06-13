---
title: Efectos de modificar la apariencia de un formulario base
ms.date: 03/30/2017
helpviewer_keywords:
- parent forms [Windows Forms]
- inherited forms [Windows Forms], modifications to base form
- Windows Forms, base form appearance
- base forms
- inheritance [Windows Forms], forms
ms.assetid: 1c3f2b29-a05c-4c6f-aa1a-4e66b94f343a
ms.openlocfilehash: 7ba4a78395bb93caa1d1d86dc135825ca2a58845
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520557"
---
# <a name="effects-of-modifying-a-base-form39s-appearance"></a>Efectos de modificar la apariencia de un formulario base
Durante el desarrollo de aplicaciones, a menudo tendrá que cambiar la apariencia del formulario base del que se heredan los demás formularios del proyecto (o de otros proyectos).  
  
 En tiempo de diseño, los cambios efectuados a la apariencia del formulario base (ya sea la configuración de propiedades o la suma y resta de controles) se reflejan en los formularios heredados al compilar el proyecto que contiene el formulario base. No basta con guardar simplemente los cambios en el formulario base. Para compilar un proyecto, elija **Compilar** en el menú **Compilar**.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
 Las modificaciones realizadas en el formulario base en tiempo de ejecución no tienen ningún efecto en los formularios heredados cuya instancia ya se ha creado.  
  
## <a name="see-also"></a>Vea también  
 [base](~/docs/csharp/language-reference/keywords/base.md)  
 [Cómo: Heredar formularios Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)  
 [Herencia visual de Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)
