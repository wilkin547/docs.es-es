---
title: "Trabajar con lenguaje de definición de datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: ec50083d-44f4-4093-9b23-5eacd601f96e
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: dc2642df7cfe0f0a4b56537d0b2ebeae34304145
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2018
---
# <a name="working-with-data-definition-language"></a>Trabajar con lenguaje de definición de datos
A partir de la [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] versión 4, el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] es compatible con el lenguaje de definición de datos (DDL). Esto le permite crear o eliminar una instancia de la base de datos basada en la cadena de conexión y los metadatos del modelo de almacenamiento (SSDL).  
  
 Los siguientes métodos de <xref:System.Data.Objects.ObjectContext> utilizan la cadena de conexión y el contenido SSDL para crear o eliminar la base de datos, comprobar si la base de datos existe y ver el script DDL generado:  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DeleteDatabase%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.DatabaseExists%2A>  
  
-   <xref:System.Data.Objects.ObjectContext.CreateDatabaseScript%2A>  
  
> [!NOTE]
>  La ejecución de los comandos DDL supone que se cuenta con los permisos necesarios.  
  
 Los métodos enumerados anteriormente delegan la mayoría del trabajo en el proveedor de datos de ADO.NET subyacente. Es responsabilidad del proveedor asegurarse de que la convención de nomenclatura utilizada para generar los objetos de base de datos es coherente con las convenciones utilizadas para las consultas y las actualizaciones.  
  
 En el siguiente ejemplo se muestra cómo generar la base de datos en función del modelo existente. También agrega un nuevo objeto entidad al contexto del objeto y, a continuación, lo guarda en la base de datos.  
  
## <a name="procedures"></a>Procedimientos  
  
#### <a name="to-define-a-database-based-on-the-existing-model"></a>Para definir una base de datos en función del modelo existente  
  
1.  Cree una aplicación de consola.  
  
2.  Agregue un modelo existente a la aplicación.  
  
    1.  Agregar un modelo vacío denominado `SchoolModel`. Para crear un modelo vacío, consulte el [Cómo: crear un nuevo archivo de .edmx](http://msdn.microsoft.com/library/beb8189e-e51c-4051-839c-9902c224abf2) tema.  
  
     El archivo SchoolModel.edmx se añade al proyecto.  
  
    1.  Copie el almacenamiento de información conceptual y asignación de contenido para el modelo School desde el [modelo School](http://msdn.microsoft.com/library/859a9587-81ea-4a45-9bc0-f8d330e1adac) tema.  
  
    2.  Abra el archivo SchoolModel.edmx y pegue el contenido dentro de las etiquetas `edmx:Runtime`.  
  
3.  Agregue el siguiente código a la función principal. El código inicializa la cadena de conexión en el servidor de bases de datos, ve el script DDL, crea la base de datos, agrega una nueva entidad al contexto y guarda los cambios en la base de datos.  
  
     [!code-csharp[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/csharp/VS_Snippets_Data/DP ObjectServices Concepts/CS/Source.cs#ddl)]
     [!code-vb[DP ObjectServices Concepts#DDL](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP ObjectServices Concepts/VB/Source.vb#ddl)]
