---
description: 'Más información acerca de: Registrar información de la aplicación (Visual Basic)'
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
ms.openlocfilehash: 6e0adf45c12d98c8bc6d177d85accf9bee347f75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99775076"
---
# <a name="logging-information-from-the-application-visual-basic"></a>Registrar información de la aplicación (Visual Basic)

Esta sección contiene temas que explican cómo registrar información sobre su aplicación usando el objeto `My.Application.Log` o `My.Log` y cómo ampliar las capacidades de registro de la aplicación.  
  
 El objeto `Log` proporciona métodos para escribir información en los agentes de escucha de registro de la aplicación y la propiedad avanzada `Log` del objeto `TraceSource` proporciona información de configuración detallada. El archivo de configuración de la aplicación configura el objeto `Log`.  
  
 El objeto `My.Log` solo está disponible para las aplicaciones ASP.NET. Para las aplicaciones cliente, use `My.Application.Log`. Para obtener más información, vea <xref:Microsoft.VisualBasic.Logging.Log>.  
  
## <a name="tasks"></a>Tareas  
  
|En|Vea|  
|--------|---------|  
|Escribir información de eventos en los registros de la aplicación.|[Cómo: Escribir mensajes de registro](how-to-write-log-messages.md)|  
|Escribir información de excepciones en los registros de la aplicación.|[Cómo: Registrar excepciones](how-to-log-exceptions.md)|  
|Escribir información de seguimiento en los registros de la aplicación cuando se inicia y se cierra la aplicación.|[Cómo: Registrar mensajes cuando se inicia o se cierra la aplicación](how-to-log-messages-when-the-application-starts-or-shuts-down.md)|  
|Configurar `My.Application.Log` para que escriba información en un archivo de texto.|[Cómo: Escribir información de eventos en un archivo de texto](how-to-write-event-information-to-a-text-file.md)|  
|Configurar `My.Application.Log` para escribir información en un registro de eventos.|[Cómo: Escribir el registro de eventos de una aplicación](how-to-write-to-an-application-event-log.md)|  
|Cambiar la ubicación dónde `My.Application.Log` escribe información.|[Tutorial: Cambiar el lugar en el que My.Application.Log escribe la información](walkthrough-changing-where-my-application-log-writes-information.md)|  
|Determinar dónde `My.Application.Log` escribe información.|[Tutorial: Determinar el lugar en el que My.Application.Log escribe la información](walkthrough-determining-where-my-application-log-writes-information.md)|  
|Crear un agente de escucha de registro personalizado para `My.Application.Log`.|[Tutorial: Crear agentes de escucha de registro personalizados](walkthrough-creating-custom-log-listeners.md)|  
|Filtrar el resultado de los registros `My.Application.Log`.|[Tutorial: Filtrar el resultado de My.Application.Log](walkthrough-filtering-my-application-log-output.md)|  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [Trabajar con registros de aplicaciones](working-with-application-logs.md)
- [Solución de problemas: agentes de escucha de registro predeterminados](troubleshooting-log-listeners.md)
