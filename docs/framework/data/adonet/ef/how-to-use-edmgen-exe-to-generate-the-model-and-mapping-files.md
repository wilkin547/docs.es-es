---
title: 'Cómo: Usar EdmGen.exe para generar los archivos de asignación y de modelo'
ms.date: 03/30/2017
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
ms.openlocfilehash: ee8297c0833378b2b44800355b47db9caa2dc7fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150524"
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>Cómo: Usar EdmGen.exe para generar los archivos de asignación y de modelo
En este tema se muestra cómo usar la herramienta EDM Generator (EdmGen.exe) para generar los siguientes archivos basados en la base de datos School:  
  
- Un modelo conceptual (un archivo .csdl).  
  
- Un modelo de almacenamiento (un archivo .ssdl).  
  
- Asignación entre los modelos conceptual y de almacenamiento (un archivo .msl).  
  
- Código del nivel de objeto en Visual Basic o C#.  
  
- Archivos de vistas.  
  
 La herramienta EdmGen.exe utiliza /mode:FullGeneration para generar los archivos enumerados anteriormente. Para obtener más información acerca de los comandos EdmGen.exe, vea Generador de [EDM (EdmGen.exe)](edm-generator-edmgen-exe.md).  
  
 Si usa EdmGen.exe para generar el modelo y los archivos de asignación, debe configurar el proyecto de Visual Studio para usar Entity Framework. Para obtener más información, vea [Cómo: configurar manualmente un proyecto](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))de Entity Framework .  
  
> [!NOTE]
> Un modelo conceptual generado mediante EdmGen.exe incluye todos los objetos de la base de datos. Si desea generar un modelo conceptual que solo incluya objetos específicos, use el asistente de Entity Data Model. Para obtener más información, vea [Cómo: usar el Asistente para Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Para generar el modelo School para un proyecto de Visual Basic con EdmGen.exe  
  
1. Cree la base de datos School. Para obtener más información, consulte [Creación de la base de](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))datos de ejemplo escolar .  
  
2. En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>Para generar el modelo School para un proyecto de C# con EdmGen.exe  
  
1. Cree la base de datos School. Para obtener más información, consulte [Creación de la base de](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100))datos de ejemplo escolar .  
  
2. En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```console  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>Consulte también

- [Modelado y asignación](modeling-and-mapping.md)
- [Cómo: Configurar manualmente un proyecto de Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Cómo: Generar previamente vistas para mejorar el rendimiento de la consulta](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [Herramientas de ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Cómo: Usar EdmGen.exe para validar los archivos de asignación y de modelo](how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
