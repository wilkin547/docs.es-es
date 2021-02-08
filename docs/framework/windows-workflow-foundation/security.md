---
description: 'Más información sobre: seguridad'
title: Seguridad
ms.date: 03/30/2017
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
ms.openlocfilehash: 8f095292deac77c1c72cf87a93064569f7dab982
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798100"
---
# <a name="security"></a>Seguridad

El almacén de instancias de flujo de trabajo de SQL usa los siguientes roles de seguridad de base de datos para garantizar el acceso a la información de estado de las instancias en la base de datos de persistencia.  
  
- **System. Activities. DurableInstancing. InstanceStoreUsers**. Este rol dispone de acceso de lectura y escritura a las vistas públicas y de derechos de ejecución en procedimientos almacenados relacionados con la creación, la carga y el almacenamiento de instancias.  
  
- **System. Activities. DurableInstancing. InstanceStoreObservers**. Este rol tiene acceso de solo lectura a las vistas públicas.  
  
- **System. Activities. DurableInstancing. WorkflowActivationUsers**. Este rol posee derechos de ejecución a procedimientos almacenados que están involucrados en el proceso de activación de instancias. Para obtener más información sobre la activación de instancias, vea [activación de instancias](instance-activation.md). La cuenta de usuario con la que se ejecuta un host genérico (como el servicio de administración de flujos de trabajo de las características de hospedaje de Windows Server AppFabric) debe agregarse a este rol de base de datos.  
  
 Para más información sobre la seguridad de los almacenes de persistencia con Windows Server App fabric, consulte [configuración de seguridad para almacenes de persistencia en App fabric](/previous-versions/appfabric/ff431727(v=azure.10)) .  
  
> [!CAUTION]
> Un cliente que tiene acceso a sus propios datos de instancia en el almacén de instancias tendrá acceso al resto de instancias en el mismo almacén de instancias. El almacén de instancias no permite especificar permisos de seguridad en el nivel de instancias. Debería crear almacenes de instancias independientes y asignar distintos grupos/usuarios para que tengan acceso a almacenes diferentes.
