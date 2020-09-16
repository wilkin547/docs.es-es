---
title: El nombre de origen especificado en EventLogSource se registra en un registro distinto del especificado en EventLogName.
ms.date: 07/20/2015
ms.assetid: 7317e100-098b-408d-86e5-7c74cf8558c7
ms.openlocfilehash: da9f1756909d1c37e28f2dde62a7f8a73bb19f37
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555645"
---
# <a name="source-name-specified-in-eventlogsource-is-registered-to-a-log-other-than-that-specified-in-eventlogname"></a>El nombre de origen especificado en EventLogSource se registra en un registro distinto del especificado en EventLogName.
El `EventLog` intenta hacer referencia a un origen que está registrado en un registro diferente. Si va a escribir entradas en un registro de eventos, debe especificar la propiedad <xref:System.Diagnostics.EventLog.Source%2A> . La propiedad <xref:System.Diagnostics.EventLog.Source%2A> registra el componente con el registro de eventos como un origen válido de entradas. Un origen único se puede asociar (y, por tanto, escribir entradas) con un único registro de eventos a la vez.  
  
 De forma predeterminada, si intenta escribir una entrada sin haber registrado primero el componente como un origen válido, el sistema automáticamente registrará el origen con el registro de eventos, usando el valor de la propiedad <xref:System.Diagnostics.EventLog.Source%2A> como la cadena de origen.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Asegúrese de que el origen está registrado en el registro correcto. Para ello, use el método <xref:System.Diagnostics.EventLog.CreateEventSource%2A> o una de sus sobrecargas para especificar una cadena que identifique de forma única el componente en el registro de eventos.  
  
## <a name="see-also"></a>Vea también

- [Administrar registros de eventos](/previous-versions/visualstudio/visual-studio-2008/4f69axw4(v=vs.90))
- [Referencias del registro de eventos](/previous-versions/visualstudio/visual-studio-2008/k43k9z2a(v=vs.90))
- [Cómo: agregar una aplicación como origen de las entradas del registro de eventos](/previous-versions/visualstudio/visual-studio-2008/xz73e171(v=vs.90))
- [Cómo: quitar un origen de eventos](/previous-versions/visualstudio/visual-studio-2008/k57466fc(v=vs.90))
