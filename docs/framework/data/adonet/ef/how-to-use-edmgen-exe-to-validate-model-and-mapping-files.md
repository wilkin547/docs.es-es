---
title: Procedimiento para usar EdmGen.exe para validar los archivos de asignación y de modelo
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: 4495ff3c5d55779e9db113a2a59361b643841382
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251376"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a>Procedimiento para usar EdmGen.exe para validar los archivos de asignación y de modelo
En este tema se muestra cómo usar la herramienta [generador de EDM (EdmGen. exe)](edm-generator-edmgen-exe.md) para validar los archivos de asignación y de modelo. Para obtener más información, vea [Entity Data Model](../entity-data-model.md).  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a>Para validar el modelo School mediante el uso de EdmGen.exe  
  
1. Cree la base de datos School. Para obtener más información, vea [crear la base de datos de ejemplo School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Genere el modelo School. Para obtener más información, consulte [Cómo Use EdmGen. exe para generar los archivos](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)de asignación y de modelo.  
  
3. En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a>Vea también

- [Cómo: Configurar manualmente un proyecto de Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [ADO.NET Entity Data Model herramientas](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Procedimientos: Generar previamente vistas para mejorar el rendimiento de las consultas](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Cómo: Usar EdmGen. exe para generar código de nivel de objeto](how-to-use-edmgen-exe-to-generate-object-layer-code.md)
