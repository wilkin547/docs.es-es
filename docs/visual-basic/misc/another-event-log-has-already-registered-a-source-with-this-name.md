---
description: 'Más información acerca de: otro registro de eventos ya ha registrado un origen con este nombre'
title: Otro registro de eventos ya ha registrado un origen con este nombre.
ms.date: 07/20/2015
ms.assetid: e6f5cd95-bb3f-4845-84fb-ae623a9bd44e
ms.openlocfilehash: ec6ae0b3ef12452a0135e5bf17dbdd5844c0f478
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787362"
---
# <a name="another-event-log-has-already-registered-a-source-with-this-name"></a>Otro registro de eventos ya ha registrado un origen con este nombre.

Se ha intentado escribir una entrada en un registro de eventos donde el origen especificado está registrado con otro registro de eventos.  
  
 Debe establecer la propiedad <xref:System.Diagnostics.EventLog.Source%2A> de la instancia de componente <xref:System.Diagnostics.EventLog> antes de que el componente escriba una entrada en un registro. Cuando ocurre esto, el sistema comprueba que el origen especificado está registrado con el registro de eventos en el que el componente está escribiendo y llama a <xref:System.Diagnostics.EventLog.CreateEventSource%2A> , si es necesario.  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1. Elimine la asociación del origen con el primer registro mediante el método <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> o <xref:System.Diagnostics.EventLog.DeleteEventSource%2A> .  
  
2. Registre el origen con el nuevo registro.  
  
## <a name="see-also"></a>Vea también

- [My. Application. log](xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.Log)
