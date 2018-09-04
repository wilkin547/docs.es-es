---
title: Seguridad
ms.date: 03/30/2017
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
ms.openlocfilehash: 6c4e64e928e3ada4210138878426fea9ffe5bdec
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43519254"
---
# <a name="security"></a>Seguridad
El almacén de instancias de flujo de trabajo de SQL usa los siguientes roles de seguridad de base de datos para garantizar el acceso a la información de estado de las instancias en la base de datos de persistencia.  
  
-   **System.Activities.DurableInstancing.InstanceStoreUsers**. Este rol dispone de acceso de lectura y escritura a las vistas públicas y de derechos de ejecución en procedimientos almacenados relacionados con la creación, la carga y el almacenamiento de instancias.  
  
-   **System.Activities.DurableInstancing.InstanceStoreObservers**. Este rol tiene acceso de solo lectura a las vistas públicas.  
  
-   **System.Activities.DurableInstancing.WorkflowActivationUsers**. Este rol posee derechos de ejecución a procedimientos almacenados que están involucrados en el proceso de activación de instancias. Para obtener más información acerca de la activación de instancias, consulte [activación de instancias](../../../docs/framework/windows-workflow-foundation/instance-activation.md). La cuenta de usuario con la que se ejecuta un host genérico (como el Servicio de administración de flujos de trabajo de [!INCLUDE[dublin](../../../includes/dublin-md.md)]) debe agregarse a este rol de la base de datos.  
  
 Para obtener más información sobre la seguridad para almacenes de persistencia con Windows Server App Fabric, consulte [configuración de seguridad para almacenes de persistencia en App Fabric](https://go.microsoft.com/fwlink/?LinkId=201208)  
  
> [!CAUTION]
>  Un cliente que tiene acceso a sus propios datos de instancia en el almacén de instancias tendrá acceso al resto de instancias en el mismo almacén de instancias. El almacén de instancias no permite especificar permisos de seguridad en el nivel de instancias. Debería crear almacenes de instancias independientes y asignar distintos grupos/usuarios para que tengan acceso a almacenes diferentes.
