---
title: "Errores en tiempo de dise&#241;o en el Dise&#241;ador de Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DTELErrorList"
  - "WhyDTELPage"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "errores en tiempo de diseño [Diseñador de Windows Forms]"
  - "errores [Diseñador de Windows Forms]"
ms.assetid: ad408380-825a-46d8-9a4a-531b130b88ce
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# Errores en tiempo de dise&#241;o en el Dise&#241;ador de Windows Forms
En este tema se explica el significado y el uso de la lista de errores en tiempo de diseño que aparece en Microsoft Visual Studio cuando se produce un error al cargar el Diseñador de Windows Forms.  Si aparece esta lista de errores, no debe interpretarla como un error del diseñador, sino como una ayuda para corregir los errores del código.  
  
 Un conocimiento básico de esta lista de errores le ayudará a depurar las aplicaciones, ya que proporciona información detallada sobre los errores y sugerencias sobre posibles soluciones.  
  
## La interfaz de lista de errores en tiempo de diseño  
 Si el Diseñador de Windows Forms no se carga, aparecerá una lista de errores en el diseñador.  Los errores están agrupados en categorías.  Por ejemplo, si tiene cuatro instancias de variables no declaradas, éstas se agruparán en la misma categoría de error.  Cada categoría de error incluye una breve descripción del error.  
  
 Puede expandir o contraer una categoría de error haciendo clic en su encabezado o en el botón de contenido adicional para expandir o contraer.  Al expandir una categoría de error, se muestra la ayuda adicional siguiente:  
  
-   Instancias del error.  
  
-   Ayuda con el error.  
  
-   Publicaciones en el foro sobre el error.  
  
### Instancias del error  
 En la ayuda adicional se muestran todas las instancias del error de su proyecto actual.  Muchos errores incluyen una ubicación exacta en el formato siguiente: *\[Nombre del proyecto\]* *\[Nombre del formulario\]* Línea:*\[Número de línea\]* Columna:*\[Número de columna\]*.  El vínculo **Ir al código** lo llevará al lugar de su código donde se ha producido el error.  
  
 Si hay una pila de llamadas asociada al error, puede hacer clic en el vínculo **Mostrar pila de llamadas**, que expande aún más el error para mostrar la pila de llamadas.  La pila puede proporcionar información valiosa sobre depuración.  Por ejemplo, puede realizar el seguimiento de las funciones a las que se llamaron antes de que se produjera el error.  La pila de llamadas se puede seleccionar para copiarla y guardarla.  
  
> [!NOTE]
>  En Visual Basic, la lista de errores en tiempo de diseño sólo muestra un error, pero puede mostrar varias instancias del mismo error.  En Visual C\+\+, los errores no tienen vínculos de código goto ni vínculos de número de línea.  
  
### Ayuda con el error  
 Si el error contiene un vínculo a un tema de la Ayuda de MSDN asociado, la ayuda adicional incluirá un vínculo al tema de Ayuda.  Al hacer clic en el vínculo, el tema de Ayuda asociado aparece en Visual Studio.  
  
### Publicaciones en el foro sobre el error  
 La ayuda adicional incluirá un vínculo a las publicaciones en el foro de MSDN relacionadas con el error.  La búsqueda en los foros se realiza a partir de la cadena del mensaje de error.  También puede intentar buscar los foros siguientes:  
  
-   [Foro de Windows Forms Designer](http://go.microsoft.com/fwlink/?LinkId=203524)  
  
-   [Foros de Windows Forms](http://go.microsoft.com/fwlink/?LinkId=203523)  
  
### Omitir y continuar  
 Puede decidir omitir el estado de error y seguir cargando el diseñador.  En tal caso, se puede producir un comportamiento inesperado.  Por ejemplo, es posible que los controles no aparezcan en la superficie de diseño.  
  
## Vea también  
 [Troubleshooting Design\-Time Development](../Topic/Troubleshooting%20Design-Time%20Development.md)   
 [Solución de problemas relacionados con la creación de controles y componentes](../../../../docs/framework/winforms/controls/troubleshooting-control-and-component-authoring.md)   
 [Desarrollar controles de formularios Windows Forms en tiempo de diseño](../../../../docs/framework/winforms/controls/developing-windows-forms-controls-at-design-time.md)   
 [Windows Forms Designer Error Messages](http://msdn.microsoft.com/es-es/cf610bf4-5fe4-471c-bce7-6a05ece07bd2)