---
title: Forma de los árboles de comandos
ms.date: 03/30/2017
ms.assetid: 2215585e-ca47-45f8-98d4-8cb982f8c1d3
ms.openlocfilehash: 8368354049a77a56a5aa54ab500619576f41b0dc
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854267"
---
# <a name="the-shape-of-the-command-trees"></a>Forma de los árboles de comandos

El módulo de generación de SQL es responsable de la generación de una consulta SQL back-end específica en función de una expresión determinada del árbol de comandos de consulta de entrada. En esta sección se describen las características, propiedades y estructura de los árboles de comandos de consulta.

## <a name="query-command-trees-overview"></a>Información general de los árboles de comandos de consulta

Un árbol de comandos de consulta es una representación del modelo de objetos de una consulta. Los árboles de comandos de consulta sirven para dos fines:

- Para expresar una consulta de entrada que se especifica en el Entity Framework.

- Expresar una consulta de salida que se proporciona a un proveedor y describe una consulta para el back-end.

Los árboles de comandos de consulta admiten una semántica más enriquecida que las consultas conformes a SQL:1999, incluso permiten trabajar con colecciones anidadas y operaciones de tipo, como por ejemplo comprobar si una entidad corresponde a un tipo determinado o filtrar conjuntos en función de un tipo.

La propiedad DBQueryCommandTree.Query es la raíz del árbol de expresiones que describe la lógica de la consulta. La propiedad DBQueryCommandTree.Parameters contiene una lista de parámetros que se utilizan en la consulta. El árbol de expresiones está compuesto por objetos DbExpression.

Un objeto DbExpression representa algún cálculo. El Entity Framework proporciona varios tipos de expresiones para crear expresiones de consulta, incluidas constantes, variables, funciones, constructores y operadores relacionales estándar como Filter y join. Cada objeto DbExpression tiene una propiedad ResultType que representa el tipo del resultado producido por esa expresión. Este tipo se expresa como TypeUsage.

## <a name="shapes-of-the-output-query-command-tree"></a>Formas del árbol de comandos de consulta de salida

Los árboles de comandos de consulta de salida representan consultas relacionales (SQL) y cumplen reglas mucho más estrictas que las que se aplican a los árboles de comandos de consulta. Por lo general contienen estructuras que se traducen con facilidad a SQL.

Los árboles de comandos de entrada se expresan con respecto al modelo conceptual, que admite propiedades de navegación, asociaciones entre entidades y herencia. Los árboles de comandos de salida se expresan con respecto al modelo de almacenamiento. Los árboles de comandos de entrada permiten proyectar colecciones anidadas, pero los árboles de comandos de salida no lo permiten.

Los árboles de comandos de consulta de salida se crean utilizando un subconjunto de los objetos DbExpression disponibles e incluso algunas expresiones en este subconjunto tienen un uso restringido.

Las operaciones de tipo, como por ejemplo comprobar si una expresión determinada es de un tipo concreto o filtrar conjuntos en función de un tipo, no se encuentran en los árboles de comandos de salida.

En los árboles de comandos de salida, solo se usan expresiones que devuelven valores booleanos para las proyecciones y únicamente en predicados de expresiones que requieren un predicado, como una instrucción de filtro o una instrucción CASE.

La raíz de un árbol de comandos de consulta de salida es un objeto DbProjectExpression.

### <a name="expression-types-not-present-in-output-query-command-trees"></a>Tipos de expresión que no están presentes en el árbol de comandos de consulta de salida

Los siguientes tipos de expresión no son válidos en un árbol de comandos de consulta de salida y no necesitan ser controlados por proveedores:

- DbDerefExpression

- DbEntityRefExpression

- DbRefKeyExpression

- DbIsOfExpression

- DbOfTypeExpression

- DbRefExpression

- DbRelationshipNavigationExpression

- DbTreatExpression

### <a name="expression-restrictions-and-notes"></a>Restricciones y notas de las expresiones

Muchas expresiones solo se pueden utilizar de una manera restringida en los árboles de comandos de consulta de salida:

#### <a name="dbfunctionexpression"></a>DbFunctionExpression

Se pueden pasar los siguientes tipos de función:

- Funciones canónicas que se reconocen en el espacio de nombres Edm.

- Funciones integradas (almacén) que se reconocen en BuiltInAttribute.

- Funciones definidas por el usuario.

Las funciones canónicas (vea [funciones canónicas](./language-reference/canonical-functions.md) para obtener más información) se especifican como parte de la Entity Framework y los proveedores deben proporcionar implementaciones para funciones canónicas basadas en esas especificaciones. Las funciones de almacén se basan en las especificaciones del manifiesto de proveedor correspondiente. Las funciones definidas por el usuario se basan en especificaciones de SSDL.

Además, las funciones con el atributo NiladicFunction no tienen ningún argumento y se deben traducir sin el paréntesis al final.  Es decir, para  *\<functionname >* en lugar de  *\<functionname > ()* .

#### <a name="dbnewinstanceexpression"></a>DbNewInstanceExpression

DbNewInstanceExpression solo se puede producir en los dos casos siguientes:

- Como la propiedad de proyección de DbProjectExpression.  Cuando se utiliza de esta forma, se aplican las siguientes restricciones:

  - El tipo de resultado debe ser un tipo de fila.

  - Cada uno de sus argumentos es una expresión que genera un resultado con un tipo primitivo. Normalmente, cada argumento es una expresión escalar, como PropertyExpression en DbVariableReferenceExpression, una invocación de función o un cálculo aritmético de DbPropertyExpression en DbVariableReferenceExpression o una invocación de función. Sin embargo, una expresión que representa una subconsulta escalar también se puede producir en la lista de argumentos para DbNewInstanceExpression. Una expresión que representa una subconsulta escalar es un árbol de expresión que representa una subconsulta que devuelve exactamente una fila y una columna de un tipo primitivo con una raíz del objeto DbElementExpression

- Con un tipo de valor devuelto de colección, en cuyo caso define una nueva colección de las expresiones proporcionadas como argumentos.

#### <a name="dbvariablereferenceexpression"></a>DbVariableReferenceExpression

DbVariableReferenceExpression tiene que ser un elemento secundario del nodo DbPropertyExpression.

#### <a name="dbgroupbyexpression"></a>DbGroupByExpression

La propiedad Aggregates de DbGroupByExpression solo puede tener elementos de tipo DbFunctionAggregate. No hay ningún otro tipo de agregado.

#### <a name="dblimitexpression"></a>DbLimitExpression

La propiedad Limite solo puede ser DbConstantExpression o DbParameterReferenceExpression. Además, el valor de la propiedad WithTies es siempre false a partir de la versión 3.5 de .NET Framework.

#### <a name="dbscanexpression"></a>DbScanExpression

Cuando se usa en árboles de comandos de salida, DbScanExpression representa eficazmente un recorrido en una tabla, una vista o una consulta de almacén, representada por EntitySetBase:: target.

Si la propiedad de metadatos "definiendo consulta" del destino no es null, representa una consulta, el texto de la consulta para el que se proporciona en esa propiedad de metadatos en el idioma específico del proveedor (o dialecto) tal y como se especifica en la definición del esquema de almacenamiento.

De lo contrario, el destino representa una tabla o una vista. El prefijo de esquema está en la propiedad de metadatos "Schema", si no es null; de lo contrario, es el nombre del contenedor de entidades.  El nombre de la tabla o vista es la propiedad de metadatos "Table", si no es null; de lo contrario, es la propiedad Name de la base del conjunto de entidades.

Todas estas propiedades proceden de la definición del elemento EntitySet correspondiente en el archivo de definición de esquemas de almacenamiento (SSDL).

### <a name="using-primitive-types"></a>Usar tipos primitivos

Cuando se hace referencia a los tipos primitivos en los árboles de comandos de salida, normalmente se hace referencia a ellos en los tipos primitivos del modelo conceptual. Sin embargo, para ciertas expresiones, los proveedores necesitan el tipo primitivo de almacén correspondiente. Entre los ejemplos de estas expresiones se encuentran DbCastExpression y posiblemente DbNullExpression, si el proveedor necesita convertir el valor NULL al tipo correspondiente. En estos casos, los proveedores deben realizar la asignación al tipo de proveedor en función de la clase del tipo primitivo y sus facetas.

## <a name="see-also"></a>Vea también

- [Generación de SQL](sql-generation.md)
