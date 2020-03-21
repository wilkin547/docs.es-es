---
title: 'Cómo: Usar EdmGen.exe para generar código de capa de objeto'
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 1dbd2e25d5f9795af4f80e079c6a0b807666743d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150563"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a>Cómo: Usar EdmGen.exe para generar código de capa de objeto
En este tema se muestra cómo utilizar la herramienta Generador de [EDM (EdmGen.exe)](edm-generator-edmgen-exe.md) para generar código de capa de objeto basado en el archivo .csdl.  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Para generar código del nivel de objeto para el modelo School en un proyecto de Visual Basic utilizando EdmGen.exe  
  
1. Cree la base de datos School. Para obtener más información, consulte [Creación de la base de](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))datos de ejemplo escolar .  
  
2. Genere el modelo School u obtenga el archivo School.csdl. Para obtener más información, vea [Cómo: Usar EdmGen.exe para generar el modelo y](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)los archivos de asignación .  
  
3. En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a>Para generar código del nivel de objeto para el modelo School en un proyecto de C# utilizando EdmGen.exe  
  
1. Cree la base de datos School. Para obtener más información, consulte [Creación de la base de](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))datos de ejemplo escolar .  
  
2. Genere el modelo School u obtenga el archivo School.csdl. Para obtener más información, vea [Cómo: Usar EdmGen.exe para generar el modelo y](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)los archivos de asignación .  
  
3. En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a>Consulte también

- [Modelado y asignación](modeling-and-mapping.md)
- [Cómo: Configurar manualmente un proyecto de Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Herramientas de Entity Data Model de ADO.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Cómo: Generar previamente vistas para mejorar el rendimiento de la consulta](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Cómo: Usar EdmGen.exe para generar los archivos de asignación y de modelo](how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
