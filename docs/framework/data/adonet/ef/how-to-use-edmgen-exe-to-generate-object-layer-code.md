---
title: Filtrar para usar EdmGen.exe para generar código de capa de objeto
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 04b35dbb5e487e573a2adfff196b79e10afdfb61
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59188235"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a>Filtrar para usar EdmGen.exe para generar código de capa de objeto
En este tema se muestra cómo usar el [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) herramienta para generar el código de capa de objeto basado en el archivo de CSDL.  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Para generar código del nivel de objeto para el modelo School en un proyecto de Visual Basic utilizando EdmGen.exe  
  
1.  Cree la base de datos School. Para obtener más información, consulte [crear la base de datos de ejemplo School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2.  Genere el modelo School u obtenga el archivo School.csdl. Para obtener más información, vea [Cómo: Usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a>Para generar código del nivel de objeto para el modelo School en un proyecto de C# utilizando EdmGen.exe  
  
1.  Cree la base de datos School. Para obtener más información, consulte [crear la base de datos de ejemplo School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2.  Genere el modelo School u obtenga el archivo School.csdl. Para obtener más información, vea [Cómo: Usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a>Vea también

- [Modelado y asignación](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [Filtrar Configurar manualmente un proyecto de Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Herramientas de ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Filtrar Generar previamente vistas para mejorar el rendimiento de las consultas](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Filtrar para usar EdmGen.exe para generar los archivos de asignación y de modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
