---
title: Procedimiento para hacer que los archivos de asignación y de modelo sean recursos incrustados
ms.date: 03/30/2017
ms.assetid: 20dfae4d-e95a-4264-9540-f5ad23b462d3
ms.openlocfilehash: bc44b4e6a2f2b2745bd3bdcb2c003a5abe1e7207
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64632055"
---
# <a name="how-to-make-model-and-mapping-files-embedded-resources"></a>Procedimiento para hacer que los archivos de asignación y de modelo sean recursos incrustados
El [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] le permite implementar los archivos de asignación y modelo como recursos incrustados de una aplicación. El ensamblado con los archivos de asignación y de modelo incrustados se debe cargar en el mismo dominio de aplicación que la conexión de entidad. Para más información, consulte [Cadenas de conexión](../../../../../docs/framework/data/adonet/ef/connection-strings.md). De forma predeterminada, las herramientas de [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] incrustan los archivos de asignación y de modelo. Cuando defina los archivos de asignación y de modelo manualmente, use este procedimiento para asegurarse de que dichos archivos se implementan como recursos incrustados junto con una aplicación de [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  
  
> [!NOTE]
>  Para mantener los recursos incrustados, deberá repetir este procedimiento cada vez que se modifiquen los archivos de asignación y de modelo.  
  
### <a name="to-embed-model-and-mapping-files"></a>Para incrustar los archivos de asignación y de modelo  
  
1. En **el Explorador de soluciones**, seleccione el archivo conceptual (.csdl).  
  
2. En el **propiedades** panel, establezca **acción de compilación** a **recurso incrustado**.  
  
3. Repita los pasos 1 y 2 para el archivo de almacenamiento (.ssdl) y el archivo de asignación (.msl).  
  
4. En **el Explorador de soluciones**, haga doble clic en el archivo App.config y, a continuación, modifique la `Metadata` parámetro en el `connectionString` atributo basado en uno de los siguientes formatos:  
  
    - `Metadata=` `res://<assemblyFullName>/<resourceName>;`  
  
    - `Metadata=` `res://*/<resourceName>;`  
  
    - `Metadata=res://*;`  
  
     Para más información, consulte [Cadenas de conexión](../../../../../docs/framework/data/adonet/ef/connection-strings.md).  
  
## <a name="example"></a>Ejemplo  
 La cadena de conexión siguiente hace referencia a un modelo incrustado y archivos de asignación para el [modelo AdventureWorks Sales](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks). Esta cadena de conexión está almacenada en el archivo App.config del proyecto.  

## <a name="see-also"></a>Vea también

- [Modelado y asignación](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md)
- [Cómo: Definir la cadena de conexión](../../../../../docs/framework/data/adonet/ef/how-to-define-the-connection-string.md)
- [Cómo: Compilar una cadena de conexión EntityConnection](../../../../../docs/framework/data/adonet/ef/how-to-build-an-entityconnection-connection-string.md)
- [Herramientas de ADO.NET Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
