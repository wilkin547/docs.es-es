---
title: Procedimiento para hacer que los archivos de asignación y de modelo sean recursos incrustados
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: c88e0c09742d76c7508d7d782eabbe46035d3501
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2019
ms.locfileid: "70251445"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a>Procedimiento para hacer que los archivos de asignación y de modelo sean recursos incrustados
[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Permite implementar archivos de asignación y de modelo como recursos incrustados de una aplicación. El ensamblado con los archivos de asignación y de modelo incrustados se debe cargar en el mismo dominio de aplicación que la conexión de entidad. Para más información, consulte [Cadenas de conexión](connection-strings.md). De forma predeterminada, las herramientas de Entity Data Model insertan los archivos de asignación y de modelo. Cuando defina los archivos de asignación y de modelo manualmente, use este procedimiento para asegurarse de que dichos archivos se implementan como recursos incrustados junto con una aplicación de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
> [!NOTE]
> Para mantener los recursos incrustados, deberá repetir este procedimiento cada vez que se modifiquen los archivos de asignación y de modelo.  
  
### <a name="to-embed-model-and-mapping-files"></a>Para incrustar los archivos de asignación y de modelo  
  
1. En **Explorador de soluciones**, seleccione el archivo conceptual (. CSDL).  
  
2. En el panel **propiedades** , establezca **acción de compilación** en **recurso incrustado**.  
  
3. Repita los pasos 1 y 2 para el archivo de almacenamiento (.ssdl) y el archivo de asignación (.msl).  
  
4. En **Explorador de soluciones**, haga doble clic en el archivo app. config y, a `Metadata` continuación, modifique `connectionString` el parámetro en el atributo basándose en uno de los siguientes formatos:  
  
    - `Metadata=``res://<assemblyFullName>/<resourceName>;`  
  
    - `Metadata=``res://*/<resourceName>;`  
  
    - `Metadata=res://*;`  
  
     Para más información, consulte [Cadenas de conexión](connection-strings.md).  
  
## <a name="example"></a>Ejemplo  
 La siguiente cadena de conexión hace referencia a los archivos de asignación y de modelo incrustados para el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks). Esta cadena de conexión está almacenada en el archivo App.config del proyecto.  

## <a name="see-also"></a>Vea también

- [Modelado y asignación](modeling-and-mapping.md)
- [Procedimientos: Definir la cadena de conexión](how-to-define-the-connection-string.md)
- [Cómo: Compilación de una cadena de conexión de EntityConnection](how-to-build-an-entityconnection-connection-string.md)
- [ADO.NET Entity Data Model herramientas](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
