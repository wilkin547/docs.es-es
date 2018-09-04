---
title: 'Cómo: Usar EdmGen.exe para generar los archivos de asignación y de modelo'
ms.date: 03/30/2017
ms.assetid: 40db462d-2fd2-4cc1-ad86-d280403e63fa
ms.openlocfilehash: 8eb7e0c19d775e516765b0e88f61789a9136e6e1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530078"
---
# <a name="how-to-use-edmgenexe-to-generate-the-model-and-mapping-files"></a>Cómo: Usar EdmGen.exe para generar los archivos de asignación y de modelo
En este tema se muestra cómo usar la herramienta EDM Generator (EdmGen.exe) para generar los siguientes archivos basados en la base de datos School:  
  
-   Un modelo conceptual (un archivo .csdl).  
  
-   Un modelo de almacenamiento (un archivo .ssdl).  
  
-   Asignación entre los modelos conceptual y de almacenamiento (un archivo .msl).  
  
-   Código del nivel de objeto en Visual Basic o C#.  
  
-   Archivos de vistas.  
  
 La herramienta EdmGen.exe utiliza /mode:FullGeneration para generar los archivos enumerados anteriormente. Para obtener más información acerca de los comandos de EdmGen.exe, vea [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).  
  
 Si usa EdmGen.exe para generar los archivos de asignación y modelo, deberá configurar el proyecto de Visual Studio para usar el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Para obtener más información, consulte [Cómo: configurar manualmente un proyecto de Entity Framework](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e).  
  
> [!NOTE]
>  Un modelo conceptual generado mediante EdmGen.exe incluye todos los objetos de la base de datos. Si desea generar un modelo conceptual que solo incluya objetos específicos, use el asistente de Entity Data Model. Para obtener más información, consulte [Cómo: usar el Asistente para Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
### <a name="to-generate-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Para generar el modelo School para un proyecto de Visual Basic con EdmGen.exe  
  
1.  Cree la base de datos School. Para obtener más información, consulte [crear la base de datos de ejemplo School](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:VB  
    ```  
  
### <a name="to-generate-the-school-model-for-a-c-project-using-edmgenexe"></a>Para generar el modelo School para un proyecto de C# con EdmGen.exe  
  
1.  Cree la base de datos School. Para obtener más información, consulte [crear la base de datos de ejemplo School](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:fullgeneration   
    /c:"Data Source=%datasourceserver%; Initial Catalog=School; Integrated Security=SSPI"   
    /project:School /entitycontainer:SchoolEntities /namespace:SchoolModel /language:CSharp  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Modelado y asignación](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)  
 [Cómo: configurar manualmente un proyecto de Entity Framework](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [Cómo: generar previamente vistas para mejorar el rendimiento de las consultas](https://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [Herramientas de Entity Data Model de ADO.NET](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [Uso de EdmGen.exe para validar los archivos de asignación y de modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-validate-model-and-mapping-files.md)
