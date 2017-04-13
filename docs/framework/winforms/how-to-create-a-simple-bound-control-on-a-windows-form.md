---
title: "C&#243;mo: Crear un control con enlace simple en Windows Forms | Microsoft Docs"
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
  - "enlace de datos, enlace de datos simple"
  - "controles de Windows Forms, enlace de datos"
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Crear un control con enlace simple en Windows Forms
Un *enlace simple* permite mostrar en un control un único elemento de datos, tal como un valor de columna de una tabla de un conjunto de datos.  Es posible enlazar de forma simple cualquier propiedad de un control a un origen de datos.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para enlazar un control de forma simple  
  
1.  Conectar con un origen de datos.  Para obtener más información, vea [Conectarse a un origen de datos](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).  
  
2.  En el formulario, seleccione el control y abra la ventana **Propiedades**.  
  
3.  Expanda la propiedad **\(DataBindings\)**.  
  
     Las propiedades enlazadas con más frecuencia se muestran bajo la propiedad **\(DataBindings\)**.  Por ejemplo, en la mayoría de controles, la propiedad **Text** suele estar enlazada.  
  
4.  Si la propiedad que desea enlazar no es una de las propiedades enlazadas habituales, haga clic en el botón **Puntos suspensivos** \(![Captura de pantalla de VisualStudioEllipsesButton](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) en el cuadro **\(Avanzadas\)** para abrir el cuadro de diálogo **Formato y enlace de datos avanzado**, que contiene una lista completa de las propiedades del control.  
  
5.  Seleccione la propiedad que desee enlazar y haga clic en la flecha de lista desplegable situada bajo **Enlace**.  
  
     Aparecerá una lista de orígenes de datos disponibles.  
  
6.  Expanda el origen de datos al que desea enlazar hasta que encuentre el elemento de datos único que desea.  Por ejemplo, si va a enlazar con un valor de columna de una tabla perteneciente a un conjunto de datos, expanda el nombre del conjunto de datos y, a continuación expanda el nombre de la tabla para mostrar nombres de columna.  
  
7.  Haga clic en el nombre de un elemento con el que se va a establecer un enlace.  
  
8.  Si está utilizando el cuadro de diálogo **Formato y enlace de datos avanzado**, haga clic en **Aceptar** para volver a la ventana **Propiedades**.  
  
9. Si desea enlazar propiedades adicionales del control, repita los pasos que van del 3 al 7.  
  
    > [!NOTE]
    >  Dado que los controles de enlace simple sólo muestran un único elemento de datos, es muy habitual incluir lógica de navegación en un Windows Form con controles de enlace simple.  
  
## Vea también  
 <xref:System.Windows.Forms.Binding>   
 [Enlace de datos en Windows Forms](../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Enlace de datos y formularios Windows Forms](../../../docs/framework/winforms/data-binding-and-windows-forms.md)