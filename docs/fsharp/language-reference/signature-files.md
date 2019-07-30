---
title: Archivos de Signatura
description: Obtenga información sobre cómo F# usar los archivos de firma para almacenar información sobre las firmas públicas de un F# conjunto de elementos de programa, como tipos, espacios de nombres y módulos.
ms.date: 06/15/2018
ms.openlocfilehash: c04ac8bf4ee360a2caa15be8f2bbea41105bd160
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627154"
---
# <a name="signatures"></a>Prototipos

Un archivo de signatura contiene información sobre las signaturas públicas de un conjunto de elementos de programa F# como, por ejemplo, tipos, espacios de nombres y módulos. Puede usarse para especificar la accesibilidad de estos elementos de programa.

## <a name="remarks"></a>Comentarios

Para cada archivo de código F#, puede tener un *archivo de signatura*, que es un archivo que tiene el mismo nombre que el archivo de código, pero con la extensión .fsi en lugar de .fs. Los archivos de signatura también se pueden agregar a la compilación de línea de comandos si usa la línea de comandos directamente. Para distinguir entre los archivos de código y de signatura, a veces los archivos de código se denominan *archivos de implementación*. En un proyecto, el archivo de signatura debe preceder al archivo de código asociado.

Un archivo de signatura describe los espacios de nombres, módulos, tipos y miembros en el archivo de implementación correspondiente. Use la información de un archivo de signatura para especificar a qué partes del código de la implementación correspondiente se puede tener acceso desde el código de fuera del archivo de implementación, así como y qué elementos son internos para el archivo de implementación. Los espacios de nombres, módulos y tipos que se incluyen en el archivo de signatura deben ser un subconjunto de los espacios de nombres, módulos y tipos que se incluyen en el archivo de implementación. Con algunas excepciones que se describen más adelante en este tema, los elementos de lenguaje que no aparecen en el archivo de signatura se consideran privados en el archivo de implementación. Si no se encuentra ningún archivo de signatura en el proyecto o en la línea de comandos, se usará la accesibilidad predeterminada.

Para obtener más información sobre la accesibilidad predeterminada, vea [Access Control](access-control.md).

En un archivo de firma no se repite la definición de los tipos y las implementaciones de cada método o función. En su lugar, use la signatura de cada método y función, que actúa como una especificación completa de la funcionalidad que se implementa mediante un fragmento del módulo o espacio de nombres. La sintaxis de una signatura de tipo es la misma que la que se usa en las declaraciones de método abstractas de interfaces y clases abstractas. Esta sintaxis también se muestra en IntelliSense y en el archivo fsi.exe intérprete de F# cuando muestra la entrada compilada correctamente.

Si no hay suficiente información en la signatura de tipo para indicar si un tipo está sellado, o si se trata de un tipo de interfaz, debe agregar un atributo que indica la naturaleza del tipo para el compilador. En la tabla siguiente se describen los atributos que se usan para este propósito.

|Atributo|DESCRIPCIÓN|
|---------|-----------|
|`[<Sealed>]`|Para un tipo que no tiene ningún miembro abstracto o que no debe ampliarse.|
|`[<Interface>]`|Para un tipo que es una interfaz.|

El compilador genera un error si los atributos no son coherentes entre la signatura y la declaración del archivo de implementación.

Use la palabra clave `val` para crear una firma para un valor o valor de función. La palabra clave `type` presenta una signatura de tipo.

Puede generar un archivo de signatura mediante la opción del compilador `--sig` . Por lo general, los archivos .fsi no se escriben manualmente. En su lugar, los archivos .fsi se generan mediante el compilador. A continuación, se agregan al proyecto, si tiene uno, y se editan quitando los métodos y las funciones que no desea que estén accesibles.

Existen varias reglas para las signaturas de tipo:

- Las abreviaturas de tipo de un archivo de implementación no deben coincidir con un tipo sin abreviatura en un archivo de signatura.

- Los registros y uniones discriminadas deben exponer todos sus campos o ninguno. Asimismo, los constructores y el orden de la signatura deben coincidir con el orden en el archivo de implementación. Las clases pueden revelar algunos, todos o ninguno de los campos y métodos de la signatura.

- Las clases y estructuras que tienen constructores deben exponer las declaraciones de sus clases base (declaración `inherits` ). Además, las clases y estructuras que tienen constructores deben exponer todas sus declaraciones de interfaz y métodos abstractos.

- Los tipos de interfaz deben revelar todos sus métodos e interfaces.

Las reglas de las signaturas de valor son las siguientes:

- Los modificadores de accesibilidad (`public`, `internal`, etc.) y los modificadores de la signatura `inline` y `mutable` deben coincidir con los de la implementación.

- El número de parámetros de tipo genérico (inferidos de manera implícita o declarados de manera explícita) deben coincidir. Asimismo, los tipos y las restricciones de los parámetros de tipo genérico también deben coincidir.

- Si se usa el atributo `Literal` , este debe aparecer en la signatura y en la implementación, y debe usarse el mismo valor literal para ambos.

- El patrón de parámetros (también conocido como *aridad*) de las signaturas y las implementaciones debe ser coherente.

- Si los nombres de parámetro de un archivo de signatura difieren del archivo de implementación correspondiente, se usará el nombre del archivo de signatura, lo que puede causar problemas al depurar o generar perfiles. Si desea recibir notificaciones de no coincidencia, habilite la advertencia 3218 en el archivo del proyecto o al invocar al compilador (vea `--warnon` en [Opciones del](compiler-options.md)compilador).

En el ejemplo de código siguiente se muestra un ejemplo de archivo de signatura que tiene el espacio de nombres, el módulo, el valor de la función y las signaturas de tipo junto con los atributos adecuados. También muestra el archivo de implementación correspondiente.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssignatures/snippet9002.fs)]

En el código siguiente se muestra el archivo de implementación.

[!code-fsharp[Main](~/samples/snippets/fsharp/fssignatures/snippet9001.fs)]

## <a name="see-also"></a>Vea también

- [Referencia del lenguaje F#](index.md)
- [Control de acceso](access-control.md)
- [Opciones del compilador](compiler-options.md)
