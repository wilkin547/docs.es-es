---
title: "Procedimientos recomendados para el control TableLayoutPanel | Microsoft Docs"
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
  - "cambiar de tamaño de forma automática"
  - "AutoSize (propiedad), TableLayoutPanel (control)"
  - "procedimientos recomendados, TableLayoutPanel (control)"
  - "controles [Windows Forms], ajustar el tamaño"
  - "formularios, procedimientos recomendados"
  - "diseño [Windows Forms]"
  - "diseño [Windows Forms], procedimientos recomendados"
  - "diseño [Windows Forms], AutoSize"
  - "ajustar el tamaño, automáticamente"
  - "TableLayoutPanel (control) [Windows Forms], procedimientos recomendados"
  - "TableLayoutPanel (control) [Windows Forms], comportamiento de AutoSize"
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Procedimientos recomendados para el control TableLayoutPanel
El control <xref:System.Windows.Forms.TableLayoutPanel> proporciona eficaces características de diseño que debería considerar cuidadosamente antes de utilizarlas en los formularios Windows Forms.  
  
## Recomendaciones  
 Las recomendaciones siguientes le ayudarán a sacar el máximo partido del control <xref:System.Windows.Forms.TableLayoutPanel>.  
  
### Uso de destino  
 Utilice el control <xref:System.Windows.Forms.TableLayoutPanel> lo menos posible.  No debería utilizarlo en todas las situaciones que requieren un diseño de tamaño variable.  En la lista siguiente se describen los diseños que sacan el máximo partido del uso del control <xref:System.Windows.Forms.TableLayoutPanel>:  
  
-   Diseños en los que hay varias partes del formulario que se cambian proporcionalmente el tamaño entre sí.  
  
-   Los diseños que se modificarán o generarán dinámicamente en tiempo de ejecución, como formularios de entrada de datos con campos personalizables por el usuario que se agreguen o quiten según las preferencias.  
  
-   Diseños que deberían permanecer en un tamaño fijo general.  Por ejemplo, puede tener un cuadro de diálogo que debería ser menor que 800 x 600, pero tiene que admitir las cadenas localizadas.  
  
 En la lista siguiente se describen diseños que no sacan demasiado partido de utilizar el control <xref:System.Windows.Forms.TableLayoutPanel>:  
  
-   Formularios de entrada de datos simples con una única columna de etiquetas y una única columna de áreas de entrada de texto.  
  
-   Formularios con una única y extensa área de presentación que debería rellenar todo el espacio disponible cuando tiene lugar un cambio de tamaño.  Un ejemplo de esto es un formulario que muestra un control <xref:System.Windows.Forms.PropertyGrid> único.  En este caso, utilice el anclaje, porque no se debería ampliar nada más cuando se cambia el tamaño del formulario.  
  
 Elija con cuidado qué controles deben estar en un control <xref:System.Windows.Forms.TableLayoutPanel>.  Si dispone de espacio para que el texto aumente en un 30% por medio de anclaje, considere usar únicamente la propiedad <xref:System.Windows.Forms.Control.Anchor%2A>.  Si puede calcular el espacio que requiere su diseño, es más fácil usar <xref:System.Windows.Forms.Control.Dock%2A> y <xref:System.Windows.Forms.Control.Anchor%2A> que calcular los detalles de espacio restante y el comportamiento de <xref:System.Windows.Forms.Control.AutoSize%2A>.  
  
 En general, cuando use un diseño con el control <xref:System.Windows.Forms.TableLayoutPanel>, manténgalo lo más sencillo que le resulte posible.  
  
### Usar la ventana Esquema del documento  
 La ventana Esquema del documento le ofrece una vista de árbol del diseño, donde puede manipular las relaciones primario\-secundario y orden z de los controles.  En el menú **Ver**, seleccione **Otras ventanas** y elija **Esquema del documento**.  
  
### Evite el anidamiento  
 Evite el anidamiento de otros controles <xref:System.Windows.Forms.TableLayoutPanel> dentro de un control <xref:System.Windows.Forms.TableLayoutPanel>.  La depuración de los diseños anidados puede plantear dificultades.  
  
### Evite la herencia visual  
 El control <xref:System.Windows.Forms.TableLayoutPanel> no admite la herencia visual en el Diseñador de Windows Forms.  Un control <xref:System.Windows.Forms.TableLayoutPanel> en una clase derivada aparece "bloqueado" en tiempo de diseño.  
  
## Vea también  
 <xref:System.Windows.Forms.TableLayoutPanel>   
 <xref:System.Windows.Forms.FlowLayoutPanel>