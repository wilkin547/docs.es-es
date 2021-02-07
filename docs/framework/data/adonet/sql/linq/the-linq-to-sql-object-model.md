---
description: 'Más información sobre: el modelo de objetos de LINQ to SQL'
title: El modelo de objetos de LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 81dd0c37-e2a4-4694-83b0-f2e49e693810
ms.openlocfilehash: be4021019d09d1479364b25268eefda50b6eaa6f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681271"
---
# <a name="the-linq-to-sql-object-model"></a>El modelo de objetos de LINQ to SQL

En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , un modelo de objetos expresado en el lenguaje de programación del programador se asigna al modelo de datos de una base de datos relacional. Así, las operaciones con los datos se realizan según el modelo de objetos.  
  
 En este escenario, no ejecuta comandos de base de datos (como `INSERT`) en la base de datos. En su lugar, cambia los valores y ejecuta los métodos de su modelo de objetos. Si desea consultar la base de datos o enviar cambios, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte sus solicitudes en los comandos SQL correctos y los envía a la base de datos.  
  
 ![Captura de pantalla que muestra el modelo de objetos de Linq.](./media/the-linq-to-sql-object-model/linq-object-model-two-tier.png)  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]En la tabla siguiente se resumen los elementos más fundamentales del modelo de objetos y su relación con los elementos del modelo de datos relacional:  
  
|Modelo de objetos LINQ to SQL|Modelo de datos relacionales|  
|------------------------------|---------------------------|  
|Clase de entidad|Tabla|  
|Miembro de clase|Columna|  
|Asociación|Relación de clave externa|  
|Método|Procedimiento almacenado o función|  
  
> [!NOTE]
> En las líneas siguientes se asume que tiene conocimientos básicos del modelo de datos relacionales y sus reglas.  
  
## <a name="linq-to-sql-entity-classes-and-database-tables"></a>Tablas de base de datos y clases de entidad en LINQ to SQL  

 En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , una tabla de base de datos se representa mediante una *clase de entidad*. Una clase de entidad es como cualquier otra clase que se pueda crear, con la salvedad de que se anota utilizando información especial que asocia la clase a una tabla de base de datos. Para realizar esta anotación, se agrega un atributo personalizado (<xref:System.Data.Linq.Mapping.TableAttribute>) a la declaración de clase, como en el ejemplo siguiente:  
  
### <a name="example"></a>Ejemplo  

 [!code-csharp[DLinqObjectModel#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#1)]
 [!code-vb[DLinqObjectModel#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#1)]  
  
 Solo las instancias de clases declaradas como tablas (es decir, clases de entidad) pueden guardarse en la base de datos.  
  
 Para obtener más información, vea la sección atributo de tabla de [asignación basada en atributos](attribute-based-mapping.md).  
  
## <a name="linq-to-sql-class-members-and-database-columns"></a>Miembros de clase y columnas de base de datos en LINQ to SQL  

 Además de asociar clases a tablas, se designan campos o propiedades para representar columnas de base de datos. Para este propósito, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] define el atributo <xref:System.Data.Linq.Mapping.ColumnAttribute>, como en el ejemplo siguiente:  
  
### <a name="example"></a>Ejemplo  

 [!code-csharp[DLinqObjectModel#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#2)]
 [!code-vb[DLinqObjectModel#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#2)]  
  
 Solo los campos y las propiedades que estén asignados a columnas se conservan en la base de datos o se recuperan de ella. Si no se han declarado como columnas, se consideran partes transitorias de la lógica de aplicación.  
  
 El atributo <xref:System.Data.Linq.Mapping.ColumnAttribute> tiene varias propiedades que se pueden utilizar para personalizar los miembros que representan columnas (por ejemplo, para designar un miembro como representativo de una columna de clave principal). Para obtener más información, vea la sección atributo de columna de [asignación basada en atributos](attribute-based-mapping.md).  
  
## <a name="linq-to-sql-associations-and-database-foreign-key-relationships"></a>Asociaciones y relaciones de clave externa de base de datos en LINQ to SQL  

 En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , las asociaciones de base de datos (como las relaciones de clave externa y clave principal) se representan mediante la aplicación del <xref:System.Data.Linq.Mapping.AssociationAttribute> atributo. En el segmento de código siguiente, la `Order` clase contiene una `Customer` propiedad que tiene un <xref:System.Data.Linq.Mapping.AssociationAttribute> atributo. Esta propiedad y su atributo proporcionan a la clase `Order` una relación con la clase `Customer`.  
  
 En el ejemplo de código siguiente se muestra la propiedad `Customer` de la clase `Order`.  
  
### <a name="example"></a>Ejemplo  

 [!code-csharp[DLinqObjectModel#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#3)]
 [!code-vb[DLinqObjectModel#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#3)]  
  
 Para obtener más información, vea la sección relativa al atributo de Asociación de [asignación basada en atributos](attribute-based-mapping.md).  
  
## <a name="linq-to-sql-methods-and-database-stored-procedures"></a>Métodos y procedimientos almacenados de base de datos en LINQ to SQL  

 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite los procedimientos almacenados y las funciones definidas por el usuario. En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] , se asignan estas abstracciones definidas por la base de datos a objetos de cliente para que se pueda tener acceso a ellas de forma fuertemente tipada a partir del código de cliente. Las firmas de método guardan la máxima similitud con las firmas de los procedimientos y funciones que se definen en la base de datos. Puede utilizar IntelliSense para detectar estos métodos.  
  
 Un conjunto de resultados devuelto por una llamada a un procedimiento asignado es una colección fuertemente tipada.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] asigna los procedimientos almacenados y las funciones a los métodos utilizando los atributos <xref:System.Data.Linq.Mapping.FunctionAttribute> y <xref:System.Data.Linq.Mapping.ParameterAttribute>. Los métodos que representan procedimientos almacenados se distinguen de los que representan funciones definidas por el usuario mediante la propiedad <xref:System.Data.Linq.Mapping.FunctionAttribute.IsComposable%2A>. Si esta propiedad se establece en `false` (valor predeterminado), el método representa un procedimiento almacenado. Si se establece en `true`, el método representa una función de base de datos.  
  
> [!NOTE]
> Si usa Visual Studio, puede usar la Object Relational Designer para crear métodos asignados a procedimientos almacenados y funciones definidas por el usuario.  
  
### <a name="example"></a>Ejemplo  

 [!code-csharp[DLinqObjectModel#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#4)]
 [!code-vb[DLinqObjectModel#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#4)]  
  
 Para obtener más información, vea las secciones atributo de función, atributo de procedimiento almacenado y atributo de parámetro de [asignación basada en atributos](attribute-based-mapping.md) y [procedimientos almacenados](stored-procedures.md).  
  
## <a name="see-also"></a>Vea también

- [Asignación basada en atributos](attribute-based-mapping.md)
- [Información general](background-information.md)
