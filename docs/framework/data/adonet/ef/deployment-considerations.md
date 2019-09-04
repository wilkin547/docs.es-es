---
title: Consideraciones de implementación (Entity Framework)
ms.date: 03/30/2017
ms.assetid: 3a847a22-4eb8-4565-b18b-453bbca070db
ms.openlocfilehash: 3e78fc413e50deda67aa8992179e500afa671f8d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251614"
---
# <a name="deployment-considerations-entity-framework"></a>Consideraciones de implementación (Entity Framework)
En este tema se proporciona información sobre cómo implementar aplicaciones que utilizan ADO.NET Entity Framework para el acceso a datos. Para obtener más información sobre el Entity Framework, vea [Introducción](getting-started.md).  
  
 Entity Framework proporciona un conjunto de herramientas que se integran con Visual Studio y facilitan el desarrollo. Para obtener más información, consulte [ADO.NET Entity Data Model Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)). En este tema no se describe cómo utilizar tecnologías concretas para implementar una aplicación basada en Entity Framework.  
  
 Visual Studio proporciona funcionalidad para distribuir e implementar aplicaciones, como la implementación ClickOnce. Para obtener más información, vea [implementar aplicaciones y componentes](/visualstudio/deployment/deploying-applications-services-and-components) en la documentación de Visual Studio.  
  
 Las consideraciones siguientes se aplican al implementar una aplicación que utiliza Entity Framework:  
  
- Entity Framework forma parte de .NET Framework a partir de .NET Framework 3.5 Service Pack 1 (SP1). Debe asegurarse de que esté instalado .NET Framework 3.5 Service Pack 1 o posterior al implementar una aplicación basada en Entity Framework.  
  
- Cuando el Asistente para Entity Data Model genera un modelo conceptual, se crea una cadena de conexión en el archivo de configuración de la aplicación. Los archivos de asignación y de modelo se pueden incrustar como recursos de aplicación o se pueden copiar en el directorio de resultados. De forma predeterminada, se implementan como recursos incrustados de la aplicación. Use la propiedad `Metadata Artifact Processing` del archivo de Entity Designer para seleccionar una de estas opciones. Para obtener más información, consulte [Cómo Copie los archivos de asignación y de modelo en](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc716709(v=vs.100))el directorio de salida.  
  
- Asegúrese de que la información sobre la asignación y el modelo (expresada en el lenguaje de definición de esquemas conceptuales (CSDL), el lenguaje de definición de esquemas de almacenamiento (SSDL) y el lenguaje de especificación de asignaciones (MSL)) se implementa junto con la aplicación y en la ubicación especificada por la cadena de conexión. Para más información, consulte [Cadenas de conexión](connection-strings.md).  
  
- Cuando se incrusta información sobre la asignación y el modelo como recursos de la aplicación, se debe recompilar e implementar la aplicación cada vez que se actualiza el modelo conceptual.  
  
- Dado que Entity Framework es un componente de .NET Framework, se puede redistribuir con la aplicación si lo permite el contrato de licencia de .NET Framework.  
  
## <a name="see-also"></a>Vea también

- [ADO.NET Entity Framework](index.md)
- [Consideraciones de desarrollo e implementación](development-and-deployment-considerations.md)
