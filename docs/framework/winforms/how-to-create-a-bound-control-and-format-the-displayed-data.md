---
title: "C&#243;mo: Crear un control enlazado y aplicar formato a los datos mostrados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles enlazados [Windows Forms], crear"
  - "controles enlazados [Windows Forms], aplicar formato a datos"
  - "datos [Windows Forms], aplicar formato"
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Crear un control enlazado y aplicar formato a los datos mostrados
Con el enlace de datos de Windows Forms, puede dar formato a los datos que se muestran en un control usando el cuadro de diálogo **Formato y enlace de datos avanzado**.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas**.  Para obtener más información, consulte [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para enlazar un control y dar formato a los datos mostrados  
  
1.  Conéctese a un origen de datos.  
  
     Para obtener más información, consulte [Conectarse a un origen de datos](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).  
  
2.  En el formulario, seleccione el control y, después, abra la ventana Propiedades.  
  
3.  Expanda la propiedad **\(DataBindings\)** y, en el cuadro **\(Avanzado\)**, haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) para mostrar el cuadro de diálogo **Formato y enlace de datos avanzado**, que muestra una lista completa de las propiedades de ese control.  
  
4.  Seleccione la propiedad que desea enlazar y haga clic en la flecha **Enlace**.  
  
     Se muestra una lista de los orígenes de datos disponibles.  
  
5.  Expanda el origen de datos al que desea enlazar hasta que encuentre el elemento de datos que desea.  
  
     Por ejemplo, si va a enlazar a un valor de columna en la tabla de un conjunto de datos, expanda el nombre del conjunto de datos y, después, expanda el nombre de la tabla para mostrar los nombres de columna.  
  
6.  Haga clic en el nombre del elemento al que se va a enlazar.  
  
7.  En el cuadro **Tipo de formato**, haga clic en el formato que desea aplicar a los datos mostrados en el control.  
  
     En cada caso, puede especificar el valor mostrado en el control si el origen de datos contiene <xref:System.DBNull>.  De lo contrario, las opciones varían ligeramente, dependiendo del tipo de formato que elija.  En la siguiente tabla se muestran los tipos de formato y las opciones.  
  
    |Tipo de formato|Opción de formato|  
    |---------------------|-----------------------|  
    |Sin formato|No hay opciones.|  
    |Numérica|Especifique el número de posiciones decimales mediante el control **Posiciones decimales**.|  
    |Moneda|Especifique el número de posiciones decimales mediante el control **Posiciones decimales**.|  
    |Fecha Hora|Seleccione cómo se deben mostrar la fecha y la hora seleccionando uno de los elementos del cuadro de selección **Tipo**.|  
    |Científica|Especifique el número de posiciones decimales mediante el control **Posiciones decimales**.|  
    |Personalizados|Especifique una cadena de formato personalizado using.<br /><br /> Para obtener más información, consulte [Aplicar formato a tipos](../../../docs/standard/base-types/formatting-types.md). **Note:**  No se garantiza que las cadenas de formato personalizado realicen correctamente el recorrido de ida y vuelta entre el origen de datos y el control enlazado.  En su lugar, controle el evento <xref:System.Windows.Forms.Binding.Parse> o <xref:System.Windows.Forms.Binding.Format> del enlace y aplique el formato personalizado en el código de control de eventos.|  
  
8.  Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Formato y enlace de datos avanzado** y volver a la ventana Propiedades.  
  
## Vea también  
 [Cómo: Crear un control con enlace simple en Windows Forms](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)   
 [User Input Validation in Windows Forms](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)   
 [Enlace de datos en Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)