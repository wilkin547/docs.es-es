---
title: Registrar información de la aplicación
ms.date: 07/20/2015
helpviewer_keywords:
- Log object
- My.Log object
- applications [Visual Basic], logging information from
- logging
- My.Application.Log object
- examples [Visual Basic], logging application information
ms.assetid: 8bf4f047-22d6-48d6-aec5-93b98ad5b8e8
ms.openlocfilehash: dace4bac3bf7529b8c50a492a092ad478f4d9e2d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74353256"
---
# <a name="logging-information-from-the-application-visual-basic"></a>Registrar información de la aplicación (Visual Basic)

Esta sección contiene temas que explican cómo registrar información sobre su aplicación usando el objeto `My.Application.Log` o `My.Log` y cómo ampliar las capacidades de registro de la aplicación.  
  
 El objeto `Log` proporciona métodos para escribir información en los agentes de escucha de registro de la aplicación y la propiedad avanzada `Log` del objeto `TraceSource` proporciona información de configuración detallada. El archivo de configuración de la aplicación configura el objeto `Log`.  
  
 El objeto `My.Log` solo está disponible para las aplicaciones ASP.NET. Para las aplicaciones cliente, use `My.Application.Log`. Para obtener más información, consulta <xref:Microsoft.VisualBasic.Logging.Log>.  
  
## <a name="tasks"></a>Tareas  
  
|Para|Vea|  
|--------|---------|  
|Escribir información de eventos en los registros de la aplicación.|[Escribir mensajes de registro](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)|  
|Escribir información de excepciones en los registros de la aplicación.|[Registrar excepciones](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)|  
|Escribir información de seguimiento en los registros de la aplicación cuando se inicia y se cierra la aplicación.|[Registrar mensajes cuando se inicia o se cierra la aplicación](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|Configurar `My.Application.Log` para que escriba información en un archivo de texto.|[Escribir información de eventos en un archivo de texto](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-event-information-to-a-text-file.md)|  
|Configurar `My.Application.Log` para escribir información en un registro de eventos.|[Cómo: Escribir el registro de eventos de una aplicación](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-to-an-application-event-log.md)|  
|Cambiar la ubicación dónde `My.Application.Log` escribe información.|[Tutorial: Cambiar el lugar donde My.Application.Log escribe información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)|  
|Determinar dónde `My.Application.Log` escribe información.|[Tutorial: Determinar el lugar en el que My.Application.Log escribe la información](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)|  
|Crear un agente de escucha de registro personalizado para `My.Application.Log`.|[Tutorial: Crear agentes de escucha de registro personalizados](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-creating-custom-log-listeners.md)|  
|Filtrar el resultado de los registros `My.Application.Log`.|[Tutorial: Filtrar el resultado de My.Application.Log](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)|  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [Trabajar con registros de aplicaciones](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [Solución de problemas: Agentes de escucha de registro](../../../../visual-basic/developing-apps/programming/log-info/troubleshooting-log-listeners.md)
