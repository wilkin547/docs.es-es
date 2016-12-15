---
title: "Solucionar problemas: Agentes de escucha del Registro (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "registros de eventos, solucionar problemas"
  - "solucionar problemas de registros de eventos"
  - "solucionar problemas de Visual Basic, registros de eventos"
ms.assetid: ac6eb760-3d5d-461e-aedd-40599ee22e49
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Solucionar problemas: Agentes de escucha del Registro (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Puede utilizar los objetos `My.Application.Log` y `My.Log` para registrar información sobre eventos que se producen en la aplicación.  
  
 Para determinar qué agentes de escucha de registro reciben esos mensajes, vea [Tutorial: Determinar el lugar en el que My.Application.Log escribe la información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md).  
  
 El objeto `Log` puede utilizar el filtrado del registro para limitar la cantidad de información que registra.  Si los filtros se configuran de forma incorrecta, los registros pueden contener información equivocada.  Para obtener más información sobre los filtros, vea [Tutorial: Filtrar el resultado de My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md).  
  
 Sin embargo, si un registro se configura incorrectamente, puede necesitar más información sobre su configuración actual.  Puede obtener esta información mediante la propiedad `TraceSource` avanzada del registro.  
  
### Para determinar los agentes de escucha de registro del objeto Log con código  
  
1.  Importe el espacio de nombres <xref:System.Diagnostics> al principio del archivo de código.  Para obtener más información, vea [Instrucción Imports \(Tipo y espacio de nombres de .NET\)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md).  
  
     [!code-vb[VbVbalrMyApplicationLog#13](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_1.vb)]  
  
2.  Cree una función que devuelva una cadena compuesta por información de cada uno de los agentes de escucha del registro.  
  
     [!code-vb[VbVbalrMyApplicationLog#14](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_2.vb)]  
  
3.  Pase la colección de los agentes de escucha de traza del registro a la función `GetListeners` y muestre el valor devuelto.  
  
     [!code-vb[VbVbalrMyApplicationLog#19](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/troubleshooting-log-listeners_3.vb)]  
  
     Para obtener más información, vea <xref:Microsoft.VisualBasic.Logging.Log.TraceSource%2A>.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Tutorial: Determinar el lugar en el que My.Application.Log escribe la información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)