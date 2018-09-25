---
title: El nombre de origen especificado en EventLogSource se registra en un registro distinto del especificado en EventLogName.
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: 03fcc41b0fbb84233aa037d7af17d168050a98b6
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47077374"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a>El nombre de origen especificado en EventLogSource se registra en un registro distinto del especificado en EventLogName.
El `EventLog` intenta hacer referencia a un origen que está registrado en un registro diferente. Si va a escribir entradas en un registro de eventos, debe especificar la propiedad <xref:System.Diagnostics.EventLog.Source%2A> . La propiedad <xref:System.Diagnostics.EventLog.Source%2A> registra el componente con el registro de eventos como un origen válido de entradas. Un origen único se puede asociar (y, por tanto, escribir entradas) con un único registro de eventos a la vez.  
  
 De forma predeterminada, si intenta escribir una entrada sin haber registrado primero el componente como un origen válido, el sistema automáticamente registrará el origen con el registro de eventos, usando el valor de la propiedad <xref:System.Diagnostics.EventLog.Source%2A> como la cadena de origen.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Asegúrese de que el origen está registrado en el registro correcto. Para ello, use el método <xref:System.Diagnostics.EventLog.CreateEventSource%2A> o una de sus sobrecargas para especificar una cadena que identifique de forma única el componente en el registro de eventos.  
  
## <a name="see-also"></a>Vea también  
 [Administración de registros de eventos](https://msdn.microsoft.com/library/35f53238-bdd2-417b-acd8-2fd9f7397f18)  
 [Referencias del registro de eventos](https://msdn.microsoft.com/library/4af0661c-6c96-49f4-961d-b26ed9bc3e87)  
 [Cómo: agregar la aplicación como un origen de entradas de registro de eventos](https://msdn.microsoft.com/library/948ff920-a739-4e66-a191-ee951512d42c)  
 [Cómo: quitar un origen de eventos](https://msdn.microsoft.com/library/bc66c900-4b8a-426a-b8e2-17031a20167e)
