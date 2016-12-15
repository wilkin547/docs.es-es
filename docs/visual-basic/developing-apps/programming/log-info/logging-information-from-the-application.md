---
title: "Registrar informaci&#243;n de la aplicaci&#243;n (Visual Basic) | Microsoft Docs"
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
  - "aplicaciones [Visual Basic], registrar información"
  - "ejemplos [Visual Basic], registrar información de aplicaciones"
  - "Log (objeto)"
  - "registro"
  - "My.Application.Log (objeto)"
  - "My.Log (objeto)"
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Registrar informaci&#243;n de la aplicaci&#243;n (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Esta sección contiene temas que explican cómo registrar información sobre su aplicación utilizando el objeto `My.Application.Log` o `My.Log` y cómo ampliar las capacidades de registro de la aplicación.  
  
 El objeto `Log` proporciona métodos para escribir información en los agentes de escucha de registro de la aplicación y la propiedad avanzada `TraceSource` del objeto `Log` proporciona información de configuración detallada.  El archivo de configuración de la aplicación configura el objeto `Log`.  
  
 El objeto `My.Log` sólo está disponible para las aplicaciones ASP.NET.  Para las aplicaciones cliente, utilice `My.Application.Log`.  Para obtener más información, vea <xref:Microsoft.VisualBasic.Logging.Log>.  
  
## Tareas  
  
|Para|Vea|  
|----------|---------|  
|Escribir información de eventos en los registros de la aplicación.|[Cómo: Escribir mensajes de registro](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)|  
|Escribir información de excepciones en los registros de la aplicación.|[Cómo: Registrar excepciones](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)|  
|Escribir información de seguimiento en los registros de la aplicación cuando se inicia y se cierra la aplicación.|[Cómo: Registrar mensajes cuando se inicia o se cierra la aplicación](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|Configurar `My.Application.Log` para que escriba información en un archivo de texto.|[Cómo: Escribir información de eventos en un archivo de texto](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)|  
|Configurar `My.Application.Log` para escribir información en un registro de eventos.|[Cómo: Escribir el registro de eventos de una aplicación](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)|  
|Cambiar la ubicación donde `My.Application.Log` escribe información.|[Tutorial: Cambiar el lugar donde My.Application.Log escribe información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)|  
|Determinar dónde escribe la información `My.Application.Log`.|[Tutorial: Determinar el lugar en el que My.Application.Log escribe la información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)|  
|Crear un agente de escucha de registro personalizado para `My.Application.Log`.|[Tutorial: Crear agentes de escucha de registro personalizados](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)|  
|Filtrar el resultado de los registros `My.Application.Log`.|[Tutorial: Filtrar el resultado de My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)|  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=fullName>   
 [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)   
 [Solución de problemas: Agentes de escucha de registro](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)