---
title: Generar SQL de modificación
ms.date: 03/30/2017
ms.assetid: 2188a39d-46ed-4a8b-906a-c9f15e6fefd1
ms.openlocfilehash: 8e0568e32094b6cc27137409f3d908928d82cebb
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43417252"
---
# <a name="modification-sql-generation"></a>Generar SQL de modificación
En esta sección se describe cómo desarrollar un módulo de generación de SQL de modificación para el proveedor (de bases de datos conformes a SQL:1999). Este módulo es responsable de la conversión de un árbol de comandos de modificación en las instrucciones INSERT, UPDATE o DELETE de SQL adecuadas.  
  
 Para obtener información sobre la generación de SQL para las instrucciones select, vea [generación de SQL](../../../../../docs/framework/data/adonet/ef/sql-generation.md).  
  
## <a name="overview-of-modification-command-trees"></a>Información general sobre los árboles de comandos de modificación  
 El módulo de generación de SQL de modificación genera instrucciones SQL de modificación específicas de la base de datos en función de un DbModificationCommandTree de entrada determinado.  
  
 DbModificationCommandTree es una representación del modelo de objetos de una operación DML de modificación (una operación de inserción, actualización o eliminación), que hereda de DbCommandTree. Hay tres implementaciones de DbModificationCommandTree:  
  
-   DbInsertCommandTree  
  
-   DbUpdateCommandTree  
  
-   DbDeleteCommandTree  
  
 DbModificationCommandTree y sus implementaciones producidos por el [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] siempre representan una operación única fila. En esta sección se describen estos tipos con sus restricciones en .NET Framework versión 3.5.  
  
 ![Diagrama](../../../../../docs/framework/data/adonet/ef/media/558ba7b3-dd19-48d0-b91e-30a76415bf5f.gif "558ba7b3-dd19-48d0-b91e-30a76415bf5f")  
  
 DbModificationCommandTree tiene una propiedad de destino que representa el conjunto de destinos para la operación de modificación. La propiedad Expression del destino, que define el conjunto de entrada, siempre es DbScanExpression.  Una expresión DbScanExpression puede representar una tabla o una vista o un conjunto de datos definidos con una consulta si la propiedad de metadatos "Definición de consulta" de su destino es distinto de null.  
  
 Una expresión DbScanExpression que representa una consulta solo puede alcanzar un proveedor como destino de la modificación si el conjunto se definió mediante una consulta de definición del modelo pero no se proporcionó ninguna función para la operación de modificación correspondiente. Es posible que los proveedores no puedan admitir este tipo de escenario (por ejemplo, SqlClient no puede).  
  
 DbInsertCommandTree representa una operación de inserción de una sola fila expresada como un árbol de comandos.  
  
```  
public sealed class DbInsertCommandTree : DbModificationCommandTree {  
   public IList<DbModificationClause> SetClauses { get }  
   public DbExpression Returning { get }  
}  
```  
  
 DbUpdateCommandTree representa una operación de actualización de una sola fila expresada como un árbol de comandos.  
  
 DbDeleteCommandTree representa una operación de eliminación de una sola fila expresada como un árbol de comandos.  
  
### <a name="restrictions-on-modification-command-tree-properties"></a>Restricciones en las propiedades del árbol de comandos de modificación  
 La información y restricciones siguientes se aplican a las propiedades del árbol de comandos de modificación.  
  
#### <a name="returning-in-dbinsertcommandtree-and-dbupdatecommandtree"></a>Returning en DbInsertCommandTree y DbUpdateCommandTree  
 Cuando no es NULL, Returning indica que el comando devuelve un lector. De lo contrario, el comando debe devolver un valor escalar que indique el número de filas afectadas (insertadas o actualizadas).  
  
 El valor de Returning especifica una proyección de resultados que se van a devolver en función de la fila insertada o actualizada. Solo puede ser de tipo DbNewInstanceExpression que representa una fila, y cada uno de sus argumentos es DbPropertyExpression en una expresión DbVariableReferenceExpression que representa una referencia al destino del árbol DbModificationCommandTree correspondiente. Las propiedades representadas por las expresiones DbPropertyExpressions utilizadas en la propiedad Returning siempre son valores calculados o generados por el almacén. En DbInsertCommandTree, Returning no es NULL cuando al menos una propiedad de la tabla en la que se inserta la fila se especifica como calculada o generada por el almacén (se marca como StoreGeneratedPattern.Identity o StoreGeneratedPattern.Computed en ssdl). En DbUpdateCommandTrees, Returning no es NULL cuando al menos una propiedad de la tabla en la que se actualiza la fila se especifica como calculada en el almacén (se marca como StoreGeneratedPattern.Computed en ssdl).  
  
#### <a name="setclauses-in-dbinsertcommandtree-and-dbupdatecommandtree"></a>SetClauses en DbInsertCommandTree y DbUpdateCommandTree  
 SetClauses especifica la lista de cláusulas de inserción o actualización que definen la operación de inserción o actualización.  
  
```  
The elements of the list are specified as type DbModificationClause, which specifies a single clause in an insert or update modification operation. DbSetClause inherits from DbModificationClause and specifies the clause in a modification operation that sets the value of a property. Beginning in version 3.5 of the .NET Framework, all elements in SetClauses are of type SetClause.   
```  
  
 Property especifica la propiedad que se debe actualizar. Siempre es DbPropertyExpression en DbVariableReferenceExpression, que representa una referencia al destino del árbol DbModificationCommandTree correspondiente.  
  
 Value especifica el nuevo valor con el que se actualiza la propiedad. Es de tipo DbConstantExpression o DbNullExpression.  
  
#### <a name="predicate-in-dbupdatecommandtree-and-dbdeletecommandtree"></a>Predicate en DbUpdateCommandTree y DbDeleteCommandTree  
 Predicate especifica el predicado que se usa para determinar qué miembros de la colección de destino se deben actualizar o eliminar. Es un árbol de expresión generado del siguiente subconjunto de DbExpressions:  
  
-   DbComparisonExpression de tipo Equals, en el que el elemento secundario derecho es DbPropertyExression según se restringe a continuación y el elemento secundario izquierdo es DbConstantExpression.  
  
-   DbConstantExpression  
  
-   DbIsNullExpression en DbPropertyExpresison tal y como se restringe a continuación  
  
-   DbPropertyExpression en DbVariableReferenceExpression, que representa una referencia al destino del árbol DbModificationCommandTree correspondiente.  
  
-   DbAndExpression  
  
-   DbNotExpression  
  
-   DbOrExpression  
  
## <a name="modification-sql-generation-in-the-sample-provider"></a>Generación de SQL de modificación en el proveedor de ejemplo  
 El [proveedor de ejemplo de Entity Framework](https://go.microsoft.com/fwlink/?LinkId=180616) muestra los componentes de proveedores de datos de ADO.NET que admiten la [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Tiene como destino una base de datos de SQL Server 2005 y se implementa como un contenedor en el proveedor de datos ADO.NET 2.0 System.Data.SqlClient.  
  
 El módulo de generación de SQL de modificación del proveedor de ejemplo (situado en el archivo SQL Generation\DmlSqlGenerator.cs) toma un árbol DbModificationCommandTree como entrada y genera una única instrucción SQL de modificación posiblemente seguida por una instrucción SELECT para devolver un lector si se especifica en DbModificationCommandTree. Observe que la base de datos de SQL Server de destino afecta a la forma de los comandos generados.  
  
### <a name="helper-classes-expressiontranslator"></a>Clases auxiliares: ExpressionTranslator  
 ExpressionTranslator actúa como un traductor ligero común para todas las propiedades del árbol de comandos de modificación de tipo DbExpression. Únicamente admite la traducción de los tipos de expresión a los que están restringidas las propiedades del árbol de comandos de modificación y se genera con las restricciones determinadas en mente.  
  
 La siguiente información describe la visita de tipos de expresión específicos (se omiten los nodos con traducciones triviales).  
  
### <a name="dbcomparisonexpression"></a>DbComparisonExpression  
 Cuando ExpressionTranslator se construye con preserveMemberValues = true y la constante de la derecha es DbConstantExpression (en lugar de DbNullExpression), asocia el operando izquierdo (DbPropertyExpressions) a DbConstantExpression. Se utiliza eso si es necesario generar una instrucción Select devuelta para identificar la fila afectada.  
  
### <a name="dbconstantexpression"></a>DbConstantExpression  
 Se crea un parámetro para cada constante visitada.  
  
### <a name="dbpropertyexpression"></a>DbPropertyExpression  
 Dado que la instancia de DbPropertyExpression siempre representa la tabla de entrada, a menos que la generación haya creado un alias (lo que solo sucede en escenarios de actualización cuando se utiliza una variable de tabla), no es necesario especificar ningún alias para la entrada; la traducción tiene como valor predeterminado el nombre de propiedad.  
  
## <a name="generating-an-insert-sql-command"></a>Generar un comando SQL de inserción  
 Para una implementación DbInsertCommandTree determinada en el proveedor de ejemplo, el comando de inserción generado sigue una de las dos plantillas de inserción siguientes.  
  
 La primera plantilla incluye un comando para realizar la inserción dados los valores de la lista de SetClauses y una instrucción SELECT para devolver las propiedades especificadas en la propiedad Returning para la fila insertada si la propiedad Returning no es NULL. El elemento de predicado "\@ @ROWCOUNT > 0" es true si se ha insertado una fila. El elemento de predicado "keyMemberI = keyValueI &#124; SCOPE_IDENTITY ()" toma la forma "keyMemberI = SCOPE_IDENTITY ()" únicamente si keyMemeberI es una clave generada por el almacén, ya que SCOPE_IDENTITY () devuelve el último valor identity insertado en una identidad () columna generada por el almacén).  
  
```  
-- first insert Template  
INSERT <target>   [ (setClauseProperty0, .. setClausePropertyN)]    
VALUES (setClauseValue0, .. setClauseValueN) |  DEFAULT VALUES   
  
[SELECT <returning>   
 FROM <target>  
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]  
```  
  
 La segunda plantilla es necesaria si la inserción especifica la inserción de una fila cuya clave principal es generada por el almacén pero no es de tipo entero y, por tanto, no se puede usar con scope_identity(). También se usa si existe una clave compuesta generada por el almacén.  
  
```  
-- second insert template  
DECLARE @generated_keys TABLE [(keyMember0, … keyMemberN)  
  
INSERT <target>   [ (setClauseProperty0, .. setClausePropertyN)]    
 OUTPUT inserted.KeyMember0, …, inserted.KeyMemberN INTO @generated_keys  
 VALUES (setClauseValue0, .. setClauseValueN) |  DEFAULT VALUES  
  
[SELECT <returning_over_t>   
 FROM @generated_keys  AS g  
JOIN <target> AS t ON g.KeyMember0 = t.KeyMember0 AND … g.KeyMemberN = t.KeyMemberN  
 WHERE @@ROWCOUNT > 0  
```  
  
 A continuación se muestra un ejemplo que utiliza el modelo incluido con el proveedor de ejemplo. Genera un comando de inserción a partir de una implementación DbInsertCommandTree.  
  
 El siguiente código inserta una categoría:  
  
```  
using (NorthwindEntities northwindContext = new NorthwindEntities()) {  
   Category c = new Category();  
   c.CategoryName = "Test Category";  
   c.Description = "A new category for testing";  
   northwindContext.AddObject("Categories", c);  
   northwindContext.SaveChanges();  
}  
```  
  
 Este código genera el siguiente árbol de comandos, que se pasa al proveedor:  
  
```  
DbInsertCommandTree  
|_Parameters  
|_Target : 'target'  
| |_Scan : dbo.Categories  
|_SetClauses  
| |_DbSetClause  
| | |_Property  
| | | |_Var(target).CategoryName  
| | |_Value  
| |   |_'Test Category'  
| |_DbSetClause  
| | |_Property  
| | | |_Var(target).Description  
| | |_Value  
| |   |_'A new category for testing'  
| |_DbSetClause  
|   |_Property  
|   | |_Var(target).Picture  
|   |_Value  
|     |_null  
|_Returning  
  |_NewInstance : Record['CategoryID'=Edm.Int32]  
    |_Column : 'CategoryID'  
      |_Var(target).CategoryID  
```  
  
 El comando de almacén que el proveedor de ejemplo genera es la siguiente instrucción SQL:  
  
```  
insert [dbo].[Categories]([CategoryName], [Description], [Picture])  
values (@p0, @p1, null)  
select [CategoryID]  
from [dbo].[Categories]  
where @@ROWCOUNT > 0 and [CategoryID] = scope_identity()  
```  
  
## <a name="generating-an-update-sql-command"></a>Generar un comando SQL de actualización  
 Para una implementación DbUpdateCommandTree determinada, el comando de actualización generado se basa en la siguiente plantilla:  
  
```  
-- UPDATE Template   
UPDATE <target>   
SET setClauseProprerty0 = setClauseValue0,  .. setClauseProprertyN = setClauseValueN  | @i = 0  
WHERE <predicate>  
  
[SELECT <returning>   
 FROM <target>  
 WHERE @@ROWCOUNT > 0 AND keyMember0 = keyValue0 AND .. keyMemberI =  keyValueI | scope_identity()  .. AND  keyMemberN = keyValueN]  
```  
  
 La cláusula set incluye la cláusula set falsa ("@i = 0") solo si no se especifica ninguna cláusula. Esto permite garantizar que las columnas calculadas en el almacén se vuelven a calcular.  
  
 Únicamente si la propiedad Returning no es NULL, se genera una instrucción SELECT para devolver las propiedades especificadas en la propiedad Returning.  
  
 En el siguiente ejemplo se utiliza el modelo que se incluye con el proveedor de ejemplo para generar un comando de actualización.  
  
 El siguiente código de usuario actualiza una categoría:  
  
```  
using (NorthwindEntities northwindContext = new NorthwindEntities()) {  
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "Test Category").First();  
   c.CategoryName = "New test name";  
   northwindContext.SaveChanges();  
}  
```  
  
 Este código de usuario genera el siguiente árbol de comandos, que se pasa al proveedor:  
  
```  
DbUpdateCommandTree  
|_Parameters  
|_Target : 'target'  
| |_Scan : dbo.Categories  
|_SetClauses  
| |_DbSetClause  
|   |_Property  
|   | |_Var(target).CategoryName  
|   |_Value  
|     |_'New test name'  
|_Predicate  
| |_  
|   |_Var(target).CategoryID  
|   |_=  
|   |_10  
|_Returning   
```  
  
 El proveedor de ejemplo genera el siguiente comando de almacén:  
  
```  
update [dbo].[Categories]  
set [CategoryName] = @p0  
where ([CategoryID] = @p1)   
```  
  
### <a name="generating-a-delete-sql-command"></a>Generar un comando SQL de eliminación  
 Para una implementación DbDeleteCommandTree determinada, el comando DELETE generado se basa en la siguiente plantilla:  
  
```  
-- DELETE Template   
DELETE <target>   
WHERE <predicate>  
```  
  
 En el siguiente ejemplo se utiliza el modelo que se incluye con el proveedor de ejemplo para generar un comando de eliminación.  
  
 El siguiente código de usuario elimina una categoría:  
  
```  
using (NorthwindEntities northwindContext = new NorthwindEntities()) {  
   Category c = northwindContext.Categories.Where(i => i.CategoryName == "New test name").First();  
   northwindContext.DeleteObject(c);  
   northwindContext.SaveChanges();  
}  
```  
  
 Este código de usuario genera el siguiente árbol de comandos, que se pasa al proveedor.  
  
```  
DbDeleteCommandTree  
|_Parameters  
|_Target : 'target'  
| |_Scan : dbo.Categories  
|_Predicate  
  |_  
    |_Var(target).CategoryID  
    |_=  
    |_10  
```  
  
 El proveedor de ejemplo genera el siguiente comando de almacén:  
  
```  
delete [dbo].[Categories]  
where ([CategoryID] = @p0)  
```  
  
## <a name="see-also"></a>Vea también  
 [Escritura de un proveedor de datos de Entity Framework](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
