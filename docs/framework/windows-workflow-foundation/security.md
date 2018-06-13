---
title: Seguridad
ms.date: 03/30/2017
ms.assetid: 737ec121-bfc5-4b75-a504-2d53c2c8af39
ms.openlocfilehash: b8fd870bcd14b8a80861914448f75fafe6af2863
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33518022"
---
# <a name="security"></a>Seguridad
El almacén de instancias de flujo de trabajo de SQL usa los siguientes roles de seguridad de base de datos para garantizar el acceso a la información de estado de las instancias en la base de datos de persistencia.  
  
-   **System.Activities.DurableInstancing.InstanceStoreUsers**. Este rol dispone de acceso de lectura y escritura a las vistas públicas y de derechos de ejecución en procedimientos almacenados relacionados con la creación, la carga y el almacenamiento de instancias.  
  
-   **System.Activities.DurableInstancing.InstanceStoreObservers**. Este rol tiene acceso de solo lectura a las vistas públicas.  
  
-   **System.Activities.DurableInstancing.WorkflowActivationUsers**. Este rol posee derechos de ejecución a procedimientos almacenados que están involucrados en el proceso de activación de instancias. Para obtener más información acerca de la activación de la instancia, consulte [activación de instancias](../../../docs/framework/windows-workflow-foundation/instance-activation.md). La cuenta de usuario con la que se ejecuta un host genérico (como el Servicio de administración de flujos de trabajo de [!INCLUDE[dublin](../../../includes/dublin-md.md)]) debe agregarse a este rol de la base de datos.  
  
 Para obtener más información acerca de la seguridad para almacenes de persistencia con Windows Server App Fabric, vea [configuración de seguridad para almacenes de persistencia en App Fabric](http://go.microsoft.com/fwlink/?LinkId=201208)  
  
> [!CAUTION]
>  Un cliente que tiene acceso a sus propios datos de instancia en el almacén de instancias tendrá acceso al resto de instancias en el mismo almacén de instancias. El almacén de instancias no permite especificar permisos de seguridad en el nivel de instancias. Debería crear almacenes de instancias independientes y asignar distintos grupos/usuarios para que tengan acceso a almacenes diferentes.
