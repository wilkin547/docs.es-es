---
title: Modelado y asignación
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: 847d518710b21df714343b541401ff7fc8443fb3
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828311"
---
# <a name="modeling-and-mapping"></a>Modelado y asignación
En [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], puede definir el modelo conceptual, el modelo de almacenamiento y la asignación entre los dos de la forma que mejor convenga a la aplicación. Las herramientas de Entity Data Model en Visual Studio permiten crear una. [archivo edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)) desde una base de datos o un modelo gráfico y, a continuación, actualice ese archivo cuando cambia la base de datos o el modelo.  
  
 A partir de Entity Framework 4.0.1 también puede crear un modelo mediante programación usando desarrollo Code First. Hay dos escenarios diferentes para el desarrollo Code First. En ambos casos, el desarrollador define un modelo codificando definiciones de clase de .NET Framework y especifica opcionalmente la asignación o configuración adicional usando anotaciones de datos o la API fluida.  
  
 Para obtener más información, consulte [crear y asignar un modelo Conceptual](https://go.microsoft.com/fwlink/?LinkId=235016).  
  
 También puede usar el generador de EDM, que se incluye con el [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)]. EdmGen.exe genera los archivos .csdl, .ssdl y .msl a partir de un origen de datos existente. También puede crear manualmente el contenido del modelo y la asignación. Para obtener más información, consulte [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).
