---
title: Procedimiento para usar EdmGen.exe para generar código de capa de objeto
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 9a73a803d310ebd847e49f4bd71609f8ef9f2944
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90546645"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a>Procedimiento para usar EdmGen.exe para generar código de capa de objeto
En este tema se muestra cómo usar la herramienta [generador de EDM (EdmGen.exe)](edm-generator-edmgen-exe.md) para generar código de nivel de objeto basado en el archivo. CSDL.  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Para generar código del nivel de objeto para el modelo School en un proyecto de Visual Basic utilizando EdmGen.exe  
  
1. Cree la base de datos School. Para obtener más información, vea [crear la base de datos de ejemplo School](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Genere el modelo School u obtenga el archivo School.csdl. Para obtener más información, vea [Cómo: usar EdmGen.exe para generar los archivos de asignación y de modelo](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3. En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a>Para generar código del nivel de objeto para el modelo School en un proyecto de C# utilizando EdmGen.exe  
  
1. Cree la base de datos School. Para obtener más información, vea [crear la base de datos de ejemplo School](/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. Genere el modelo School u obtenga el archivo School.csdl. Para obtener más información, vea [Cómo: usar EdmGen.exe para generar los archivos de asignación y de modelo](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3. En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a>Vea también

- [Modelado y asignación](modeling-and-mapping.md)
- [Cómo: Configurar manualmente un proyecto de Entity Framework](/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Herramientas de Entity Data Model de ADO.NET](/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Cómo: Generar previamente vistas para mejorar el rendimiento de la consulta](/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Procedimiento para usar EdmGen.exe para generar los archivos de asignación y de modelo](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
