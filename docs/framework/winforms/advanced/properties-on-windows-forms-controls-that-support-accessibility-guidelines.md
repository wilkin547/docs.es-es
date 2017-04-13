---
title: "Propiedades de los controles de formularios Windows Forms que admiten las directrices de accesibilidad | Microsoft Docs"
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
  - "accesibilidad, propiedades de los controles de Windows Forms"
  - "Windows Forms, propiedades de accesibilidad de los controles"
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# Propiedades de los controles de formularios Windows Forms que admiten las directrices de accesibilidad
Los controles del cuadro de herramientas estándar para formularios Windows Forms admiten muchas de las directrices de accesibilidad, entre ellas la exposición del foco del teclado y de los elementos de la pantalla.  
  
## Planear la accesibilidad  
 Puede utilizar las propiedades de los controles para ofrecer compatibilidad con otras directrices de accesibilidad, como se muestra en la tabla siguiente.  Además, es recomendable utilizar menús para proporcionar acceso a las características del programa.  
  
|Propiedad de control|Consideraciones para la accesibilidad|  
|--------------------------|-------------------------------------------|  
|AccessibleDescription|Descripción que se ofrece a las ayudas de accesibilidad, tales como los lectores de pantalla.  Las ayudas de accesibilidad son programas y dispositivos especializados, que ayudan a las personas con discapacidades a utilizar de forma más eficiente los equipos.|  
|AccessibleName|Nombre que se ofrece a las ayudas de accesibilidad.|  
|AccessibleRole|Describe el uso del elemento en la interfaz de usuario.|  
|TabIndex|Crea una ruta de desplazamiento razonable a través del formulario.  Es importante que los controles que no tienen etiquetas intrínsecas, tales como los cuadros de texto, vayan precedidos de forma inmediata en el orden de tabulación por sus etiquetas asociadas.|  
|Text|Utilice el carácter "&" para crear teclas de acceso.  El uso de teclas de acceso forma parte de la tarea de proporcionar acceso documentado mediante teclado a las características.|  
|FontSize|Si no es posible ajustar el tamaño de la fuente, debe establecerse en 10 puntos o más.  Una vez establecido el tamaño de la fuente del formulario, todos los controles que se agreguen a continuación al formulario tendrán el mismo tamaño.|  
|Forecolor|Si se establece esta propiedad en el valor predeterminado, el formulario utilizará las preferencias de color del usuario.|  
|Backcolor|Si se establece esta propiedad en el valor predeterminado, el formulario utilizará las preferencias de color del usuario.|  
|BackgroundImage|Deje esta propiedad en blanco para que el texto resulte más legible.|  
  
## Vea también  
 [Tutorial: Crear una aplicación accesible basada en Windows](../../../../docs/framework/winforms/advanced/walkthrough-creating-an-accessible-windows-based-application.md)