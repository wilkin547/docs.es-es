---
title: Procedimiento para usar EdmGen.exe para generar los archivos de asignación y de modelo
ms.date: 03/30/2017
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
ms.openlocfilehash: 37234d8f0631ea11ea0d9c7d4e8f027a7266814e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69958452"
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>Procedimiento para usar EdmGen.exe para generar los archivos de asignación y de modelo
En este tema se muestra cómo usar la herramienta EDM Generator (EdmGen.exe) para generar los siguientes archivos basados en la base de datos School:  
  
- Un modelo conceptual (un archivo .csdl).  
  
- Un modelo de almacenamiento (un archivo .ssdl).  
  
- Asignación entre los modelos conceptual y de almacenamiento (un archivo .msl).  
  
- Código del nivel de objeto en Visual Basic o C#.  
  
- Archivos de vistas.  
  
 La herramienta EdmGen.exe utiliza /mode:FullGeneration para generar los archivos enumerados anteriormente. Para obtener más información acerca de los comandos de EdmGen. exe, vea [generador de EDM (EdmGen. exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).  
  
 Si usa EdmGen. exe para generar los archivos de asignación y de modelo, tendrá que configurar el proyecto de Visual Studio para que use [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Para obtener más información, vea [Cómo: Configurar manualmente un proyecto](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))de Entity Framework.  
  
> [!NOTE]
> Un modelo conceptual generado mediante EdmGen.exe incluye todos los objetos de la base de datos. Si desea generar un modelo conceptual que solo incluya objetos específicos, use el asistente de Entity Data Model. Para obtener más información, vea [Cómo: Use el Asistente para](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100))Entity Data Model.  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Para generar el modelo School para un proyecto de Visual Basic con EdmGen.exe  
  
1. Cree la base de datos School. Para obtener más información, vea [crear la base de datos de ejemplo School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>Para generar el modelo School para un proyecto de C# con EdmGen.exe  
  
1. Cree la base de datos School. Para obtener más información, vea [crear la base de datos de ejemplo School](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399731(v=vs.100)).  
  
2. En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>Vea también

- [Modelado y asignación](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [Cómo: Configurar manualmente un proyecto de Entity Framework](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738546(v=vs.100))
- [Cómo: Generar previamente vistas para mejorar el rendimiento de las consultas](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896240(v=vs.100))
- [ADO.NET Entity Data Model herramientas](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Procedimientos: Usar EdmGen. exe para validar los archivos de asignación y de modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
