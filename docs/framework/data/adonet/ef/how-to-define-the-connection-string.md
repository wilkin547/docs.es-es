---
title: "Cómo: Definir la cadena de conexión"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6027335d-4e26-420d-9151-6523289b1989
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: c7c17029dade53c724420fa5604ba3448ce6a6ab
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-define-the-connection-string"></a>Cómo: Definir la cadena de conexión
En este tema se muestra cómo definir la cadena de conexión que se usa al conectarse a un modelo conceptual. En este tema se basa en el [AdventureWorks Sales](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) modelo conceptual. El modelo AdventureWorks Sales se usa en todos los temas relacionados con tareas de la documentación de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. En este tema se da por supuesto que ya ha configurado la [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] y define el modelo AdventureWorks Sales. Para obtener más información, consulte [Cómo: definir manualmente los archivos de asignación y modelo](http://msdn.microsoft.com/en-us/d4fd6864-f2a1-48f0-aa32-1e318775a99a). Los procedimientos descritos en este tema también se incluyen en [Cómo: configurar manualmente un proyecto de Entity Framework](http://msdn.microsoft.com/en-us/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
> [!NOTE]
>  Si usa el Asistente para [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] en un proyecto de [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)], el asistente genera automáticamente un archivo .edmx y configura el proyecto para que use [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Para obtener más información, vea [Cómo: usar el Asistente para Entity Data Model](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d)  
  
### <a name="to-define-the-entity-framework-connection-string"></a>Para definir la cadena de conexión de Entity Framework  
  
-   Abra el archivo de configuración de la aplicación del proyecto (app.config) y, a continuación, agregue la siguiente cadena de conexión:  
  
  
  
     Si el proyecto no tiene un archivo de configuración de aplicación, puede agregar uno seleccionando **Agregar nuevo elemento** desde el **proyecto** menú, seleccione la **General** categoría, seleccionar **archivo de configuración de aplicación**y, a continuación, haga clic en **agregar**.  
  
## <a name="see-also"></a>Vea también  
 [Inicio rápido](http://msdn.microsoft.com/en-us/0bc534be-789f-4819-b9f6-76e51d961675)  
 [Cómo: crear un nuevo archivo .edmx](http://msdn.microsoft.com/en-us/beb8189e-e51c-4051-839c-9902c224abf2)  
 [Herramientas de Entity Data Model de ADO.NET](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)
