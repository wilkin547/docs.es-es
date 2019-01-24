---
title: Procedimiento Usar EdmGen.exe para generar código de nivel de objeto
ms.date: 03/30/2017
ms.assetid: c44d2ebe-f66f-42cb-9741-4a3f0c2dcffb
ms.openlocfilehash: 63542866441cb347362e64b08b5de11bde19d50b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654573"
---
# <a name="how-to-use-edmgenexe-to-generate-object-layer-code"></a>Procedimiento Usar EdmGen.exe para generar código de nivel de objeto
En este tema se muestra cómo usar el [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) herramienta para generar el código de capa de objeto basado en el archivo de CSDL.  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-visual-basic-project-using-edmgenexe"></a>Para generar código del nivel de objeto para el modelo School en un proyecto de Visual Basic utilizando EdmGen.exe  
  
1.  Cree la base de datos School. Para obtener más información, consulte [crear la base de datos de ejemplo School](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Genere el modelo School u obtenga el archivo School.csdl. Para obtener más información, vea [Cómo: Usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.vb /language:VB  
    ```  
  
### <a name="to-generate-object-layer-code-for-the-school-model-for-a-c-project-using-edmgenexe"></a>Para generar código del nivel de objeto para el modelo School en un proyecto de C# utilizando EdmGen.exe  
  
1.  Cree la base de datos School. Para obtener más información, consulte [crear la base de datos de ejemplo School](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Genere el modelo School u obtenga el archivo School.csdl. Para obtener más información, vea [Cómo: Usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```  
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:EntityClassGeneration   
    /incsdl:.\School.csdl /outobjectlayer:.\School.Objects.cs /language:CSharp  
    ```  
  
## <a name="see-also"></a>Vea también
- [Modelado y asignación](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [Cómo: Configurar manualmente un proyecto de Entity Framework](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)
- [Herramientas de Entity Data Model de ADO.NET](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)
- [Cómo: Generar previamente vistas para mejorar el rendimiento de las consultas](https://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)
- [Cómo: Usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md)
