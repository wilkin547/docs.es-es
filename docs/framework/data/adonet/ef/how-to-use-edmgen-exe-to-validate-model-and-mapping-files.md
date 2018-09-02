---
title: 'Cómo: Usar EdmGen.exe para validar los archivos de asignación y de modelo'
ms.date: 03/30/2017
ms.assetid: 2641906a-971a-4d0b-8aee-13fabc02a1cc
ms.openlocfilehash: fda8698381e98c64318f1a26f77f0263e9085074
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2018
ms.locfileid: "43471931"
---
# <a name="how-to-use-edmgenexe-to-validate-model-and-mapping-files"></a>Cómo: Usar EdmGen.exe para validar los archivos de asignación y de modelo
En este tema se muestra cómo usar el [EDM Generator (EdmGen.exe)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md) herramienta para validar los archivos de asignación y modelo. Para obtener más información, consulte [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md).  
  
### <a name="to-validate-the-school-model-using-edmgenexe"></a>Para validar el modelo School mediante el uso de EdmGen.exe  
  
1.  Cree la base de datos School. Para obtener más información, consulte [crear la base de datos de ejemplo School](https://msdn.microsoft.com/library/c1bec483-a0ea-4660-aa0b-7b0a8b68fed0).  
  
2.  Genere el modelo School. Para obtener más información, consulte [Cómo: usar EdmGen.exe para generar los archivos de asignación y modelo](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-the-model-and-mapping-files.md).  
  
3.  En el símbolo del sistema, ejecute el comando siguiente sin los saltos de línea:  
  
    ```console
    "%windir%\Microsoft.NET\Framework\v4.0.30319\edmgen.exe" /mode:ValidateArtifacts /inssdl:.\School.ssdl /inmsl:.\School.msl /incsdl:.\School.csdl  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Cómo: configurar manualmente un proyecto de Entity Framework](https://msdn.microsoft.com/library/73f6ae1d-b3b2-4577-aebd-ad5a75954e9e)  
 [Herramientas de Entity Data Model de ADO.NET](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [Cómo: generar previamente vistas para mejorar el rendimiento de las consultas](https://msdn.microsoft.com/library/b18a9d16-e10b-4043-ba91-b632f85a2579)  
 [Uso de EdmGen.exe para generar código de capa de objeto](../../../../../docs/framework/data/adonet/ef/how-to-use-edmgen-exe-to-generate-object-layer-code.md)
