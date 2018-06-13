---
title: 'Cómo: Crear un control enlazado y aplicar formato a los datos mostrados'
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: 9055ec9c4b646e0c86819e4e72db8ce20086bace
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542215"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a>Cómo: Crear un control enlazado y aplicar formato a los datos mostrados
Con el enlace de datos de formularios Windows Forms, puede dar formato a los datos mostrados en un control enlazado a datos mediante el uso de la **formato y enlace avanzada** cuadro de diálogo.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, vea [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-bind-a-control-and-format-the-displayed-data"></a>Para enlazar un control y dar formato a los datos mostrados  
  
1.  Conéctese a un origen de datos.  
  
     Para obtener más información, consulte [conectarse a un origen de datos](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).  
  
2.  En el formulario, seleccione el control y, después, abra la ventana Propiedades.  
  
3.  Expanda el **(DataBindings)** propiedad y, a continuación, en la **(avanzado)** cuadro, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton] (../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) para mostrar el **formato y enlace de datos avanzado** cuadro de diálogo que muestra una lista completa de propiedades de ese control.  
  
4.  Seleccione la propiedad que desea enlazar y, a continuación, haga clic en el **enlace** flecha.  
  
     Se muestra una lista de los orígenes de datos disponibles.  
  
5.  Expanda el origen de datos al que desea enlazar hasta que encuentre el elemento de datos que desea.  
  
     Por ejemplo, si va a enlazar a un valor de columna en la tabla de un conjunto de datos, expanda el nombre del conjunto de datos y, después, expanda el nombre de la tabla para mostrar los nombres de columna.  
  
6.  Haga clic en el nombre del elemento al que se va a enlazar.  
  
7.  En el **dar formato a tipo** cuadro, haga clic en el formato que desea aplicar a los datos mostrados en el control.  
  
     En cada caso, puede especificar el valor mostrado en el control si el origen de datos contiene <xref:System.DBNull>. De lo contrario, las opciones varían ligeramente, dependiendo del tipo de formato que elija. En la siguiente tabla se muestran los tipos de formato y las opciones.  
  
    |Tipo de formato|Opción de formato|  
    |-----------------|-----------------------|  
    |Sin formato|No hay opciones.|  
    |Numérica|Especificar el número de posiciones decimales mediante **decimales** control de flechas.|  
    |Moneda|Especificar el número de posiciones decimales mediante **decimales** control de flechas.|  
    |Fecha Hora|Seleccione cómo se deben mostrar la fecha y hora seleccionando uno de los elementos en el **tipo** cuadro de selección.|  
    |Científica|Especificar el número de posiciones decimales mediante **decimales** control de flechas.|  
    |Personalizados|Especifique una cadena de formato personalizado using.<br /><br /> Para obtener más información, consulte [Aplicar formato a tipos](../../../docs/standard/base-types/formatting-types.md). **Nota:** correctamente de ida y vuelta entre el origen de datos y el control enlazado no se garantiza que las cadenas de formato personalizado. En su lugar, controle el evento <xref:System.Windows.Forms.Binding.Parse> o <xref:System.Windows.Forms.Binding.Format> del enlace y aplique el formato personalizado en el código de control de eventos.|  
  
8.  Haga clic en **Aceptar** para cerrar el **formato y enlace de datos avanzado** cuadro de diálogo y volver a la ventana Propiedades.  
  
## <a name="see-also"></a>Vea también  
 [Crear un control con enlace simple en Windows Forms](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)  
 [Validación de los datos proporcionados por el usuario Windows Forms](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)  
 [Enlace de datos en Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)
