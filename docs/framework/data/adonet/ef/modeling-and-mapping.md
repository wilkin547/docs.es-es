---
title: Modelado y asignación
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: 88c8786a5e538d8441e03e46e59743e4c489b4c5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32762941"
---
# <a name="modeling-and-mapping"></a>Modelado y asignación
En [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], puede definir el modelo conceptual, el modelo de almacenamiento y la asignación entre los dos de la forma que mejor convenga a la aplicación. Las herramientas de Entity Data Model en Visual Studio le permiten crear una. [archivo edmx](http://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4) desde una base de datos o una modelo gráfico y, a continuación, actualizar ese archivo cuando cambia la base de datos o el modelo.  
  
 A partir de Entity Framework 4.0.1 también puede crear un modelo mediante programación usando desarrollo Code First. Hay dos escenarios diferentes para el desarrollo Code First. En ambos casos, el desarrollador define un modelo codificando definiciones de clase de .NET Framework y especifica opcionalmente la asignación o configuración adicional usando anotaciones de datos o la API fluida.  
  
 Para obtener más información, consulte [crear y asignar un modelo Conceptual](http://go.microsoft.com/fwlink/?LinkId=235016).  
  
 También puede usar el generador de EDM, que se incluye con la [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]. EdmGen.exe genera los archivos .csdl, .ssdl y .msl a partir de un origen de datos existente. También puede crear manualmente el contenido del modelo y la asignación. Para obtener más información, consulte [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).
