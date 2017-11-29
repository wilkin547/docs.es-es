---
title: Otro registro de eventos ya ha registrado un origen con este nombre.
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8beea344d233794ddc36d7fc53db1c01be84399f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a>Otro registro de eventos ya ha registrado un origen con este nombre.
Se ha intentado escribir una entrada en un registro de eventos donde el origen especificado está registrado con otro registro de eventos.  
  
 Debe establecer la propiedad <xref:System.Diagnostics.EventLog.Source%2A> de la instancia de componente <xref:System.Diagnostics.EventLog> antes de que el componente escriba una entrada en un registro. Cuando ocurre esto, el sistema comprueba que el origen especificado está registrado con el registro de eventos en el que el componente está escribiendo y llama a <xref:System.Diagnostics.EventLog.CreateEventSource%2A> , si es necesario.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Elimine la asociación del origen con el primer registro mediante el método <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> o <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> .  
  
2.  Registre el origen con el nuevo registro.  
  
## <a name="see-also"></a>Vea también  
 [My.Application.Log (objeto)](../../visual-basic/language-reference/objects/my-application-log-object.md)  
 [Cómo: quitar un origen de eventos](http://msdn.microsoft.com/en-us/bc66c900-4b8a-426a-b8e2-17031a20167e)  
 [Cómo: agregar la aplicación como un origen de entradas de registro de eventos](http://msdn.microsoft.com/en-us/948ff920-a739-4e66-a191-ee951512d42c)
