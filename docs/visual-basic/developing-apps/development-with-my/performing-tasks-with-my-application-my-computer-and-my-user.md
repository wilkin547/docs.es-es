---
title: "Realizar tareas con My.Application, My.Computer y My.User (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Application (objeto), desarrollar aplicaciones"
  - "My.Computer (objeto), desarrollar aplicaciones"
  - "My.User (objeto), desarrollar aplicaciones"
  - "desarrollo rápido de aplicaciones (RAD), My.Application"
  - "desarrollo rápido de aplicaciones (RAD), My.Computer"
  - "desarrollo rápido de aplicaciones (RAD), My.User"
ms.assetid: c8af61bd-4dd3-4a0f-9af5-795b594b240b
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Realizar tareas con My.Application, My.Computer y My.User (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Los tres objetos `My` centrales que proporcionan acceso a información y funcionalidad de uso frecuente son `My.Application` \(<xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>\), `My.Computer` \(<xref:Microsoft.VisualBasic.Devices.Computer>\) y `My.User` \(<xref:Microsoft.VisualBasic.ApplicationServices.User>\).  Puede utilizar estos objetos para tener acceso a información relacionada con la aplicación actual, con el equipo donde está instalada la aplicación o con el usuario actual de la aplicación, respectivamente.  
  
## My.Application, My.Computer y My.User  
 Los ejemplos siguientes muestran cómo se puede recuperar información utilizando `My`.  
  
 [!code-vb[VbVbcnMy#1](../../../visual-basic/developing-apps/development-with-my/codesnippet/visualbasic/performing-tasks-with-my_1.vb)]  
  
 [!code-vb[VbVbcnMy#2](../../../visual-basic/developing-apps/development-with-my/codesnippet/visualbasic/performing-tasks-with-my_2.vb)]  
  
 Además de recuperar información, los miembros expuestos a través de estos tres objetos también permiten ejecutar métodos relacionados con ese objeto.  Por ejemplo, puede tener acceso a una variedad de métodos para manipular archivos o actualizar el Registro a través de `My.Computer`.  
  
 La E\/S de archivos resulta mucho más sencilla y rápida con `My`, que incluye una variedad de métodos y propiedades para manipular archivos, directorios y unidades.  El objeto <xref:Microsoft.VisualBasic.FileIO.TextFieldParser> permite leer en archivos estructurados grandes con campos delimitados o de ancho fijo.  En este ejemplo se abre `TextFieldParser` `reader`, que se utiliza para leer `C:\TestFolder1\test1.txt`.  
  
 [!code-vb[VbVbalrTextFieldParser#23](../../../visual-basic/developing-apps/development-with-my/codesnippet/visualbasic/performing-tasks-with-my_3.vb)]  
  
 `My.Application` permite cambiar la referencia cultural de la aplicación.  El ejemplo siguiente muestra cómo se puede llamar a este método.  
  
 [!code-vb[VbVbcnMy#3](../../../visual-basic/developing-apps/development-with-my/codesnippet/visualbasic/performing-tasks-with-my_4.vb)]  
  
## Vea también  
 <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.ApplicationServices.User>   
 [Cómo My depende del tipo de proyecto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)