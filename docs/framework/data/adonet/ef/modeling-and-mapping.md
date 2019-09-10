---
title: Modelado y asignación
ms.date: 03/30/2017
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
ms.openlocfilehash: 133539ab1b6d6f2f0ab3f8deed5b22240c2bb07e
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854392"
---
# <a name="modeling-and-mapping"></a>Modelado y asignación
En el Entity Framework, puede definir el modelo conceptual, el modelo de almacenamiento y la asignación entre los dos de la forma que mejor se adapte a su aplicación. Las herramientas de Entity Data Model de Visual Studio le permiten crear un. [archivo edmx](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100)) de una base de datos o un modelo gráfico y, a continuación, actualice el archivo cuando cambie la base de datos o el modelo.  
  
 A partir de Entity Framework 4.0.1 también puede crear un modelo mediante programación usando desarrollo Code First. Hay dos escenarios diferentes para el desarrollo Code First. En ambos casos, el desarrollador define un modelo codificando definiciones de clase de .NET Framework y especifica opcionalmente la asignación o configuración adicional usando anotaciones de datos o la API fluida.  
  
 Para obtener más información, vea [crear y asignar un modelo conceptual](https://go.microsoft.com/fwlink/?LinkId=235016).  
  
 También puede usar el generador de EDM, que se incluye con el .NET Framework. EdmGen.exe genera los archivos .csdl, .ssdl y .msl a partir de un origen de datos existente. También puede crear manualmente el contenido del modelo y la asignación. Para obtener más información, vea [generador de EDM (EdmGen. exe)](edm-generator-edmgen-exe.md).
