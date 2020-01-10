---
title: 'Tipos de cambios importantes: .NET Core'
description: Obtenga más información sobre los esfuerzos de .NET Core por mantener la compatibilidad entre versiones de .NET para los desarrolladores, así como sobre los tipos de cambios que se consideran importantes.
ms.date: 06/10/2019
ms.openlocfilehash: a84468c0c0e04f367dc7e89ce806ac01b2b49b48
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740897"
---
# <a name="changes-that-affect-compatibility"></a>Cambios que afectan a la compatibilidad

A lo largo de su historia, .NET ha intentado mantener un alto nivel de compatibilidad de versión a versión y a través de los sabores de .NET. Esto sigue siendo cierto para .NET Core. Aunque .NET Core se puede considerar como una nueva tecnología que es independiente de .NET Framework, hay dos factores principales que limitan la capacidad de .NET Core para desviarse de .NET Framework:

- Un gran número de desarrolladores desarrollaron originalmente o continúan desarrollando aplicaciones .NET Framework. Esperan un comportamiento coherente en las implementaciones de .NET.

- Los proyectos de bibliotecas .NET Standard permiten a los desarrolladores crear bibliotecas dirigidas a las API comunes compartidas por .NET Core y .NET Framework. Los desarrolladores esperan que una biblioteca utilizada en una aplicación .NET Core se comporte de forma idéntica a la misma biblioteca utilizada en una aplicación .NET Framework.

Junto con la compatibilidad entre las implementaciones de .NET, los desarrolladores esperan un alto nivel de compatibilidad entre las versiones .NET Core. En particular, el código escrito para una versión anterior de .NET Core debería funcionar sin problemas en una versión posterior de .NET Core. De hecho, muchos desarrolladores esperan que las nuevas API que se encuentran en las versiones más recientes de .NET Core también sean compatibles con las versiones preliminares en las que se introdujeron dichas API.

En este artículo se describen las categorías de cambios de compatibilidad (o cambios importantes) y la forma en que el equipo de .NET evalúa los cambios en cada una de estas categorías. Entender cómo el equipo de .NET aborda los posibles cambios importantes es particularmente útil para los desarrolladores que abren solicitudes de incorporación de cambios en el repositorio de GitHub [dotnet/runtime](https://github.com/dotnet/runtime) que tienen por objetivo modificar el comportamiento de las API existentes.

> [!NOTE]
> Para una definición de las categorías de compatibilidad, como la compatibilidad binaria y la compatibilidad con versiones anteriores, consulte [Breaking change categories](categories.md) (Categorías de cambios importantes).

En las secciones siguientes se describen las categorías de los cambios realizados en las API de .NET Core y su impacto sobre la compatibilidad de aplicaciones. El icono ✔️ indica que se permite un determinado tipo de cambio, ❌ indica que no se permite y ❓ indica un cambio que puede permitirse o no. Los cambios en esta última categoría requieren un criterio y una evaluación de cuán predecible, obvio y coherente era el comportamiento anterior.

> [!NOTE]
> Además de servir como guía para evaluar los cambios en las bibliotecas .NET Core, los desarrolladores de bibliotecas también pueden utilizar estos criterios para evaluar los cambios en sus bibliotecas que tienen como objetivo varias implementaciones y versiones de .NET.

## <a name="modifications-to-the-public-contract"></a>Modificaciones en el contrato público

Los cambios en esta categoría modifican el área expuesta pública de un tipo. No están permitidos la mayoría de los cambios en esta categoría ya que infringen la *compatibilidad con versiones anteriores* (la capacidad de una aplicación que se ha desarrollado con una versión anterior de una API para ejecutarse sin recompilación en una versión posterior).

### <a name="types"></a>Tipos

- **✔️ Supresión de una implementación de interfaz de un tipo cuando la interfaz ya está implementada por un tipo base**

- **❓ Adición de una nueva implementación de interfaz a un tipo**

  Este es un cambio aceptable porque no afecta negativamente a los clientes existentes. Cualquier cambio en el tipo debe funcionar dentro de los límites de los cambios aceptables definidos aquí para que la nueva implementación siga siendo aceptable. Es necesario extremar las precauciones cuando se agregan interfaces que afectan directamente a la capacidad de un diseñador o serializador para generar código o datos que no se pueden consumir a un nivel inferior. Un ejemplo es la interfaz <xref:System.Runtime.Serialization.ISerializable>.

- **❓ Introducción a una nueva clase base**

  Un tipo puede introducirse en una jerarquía entre dos tipos existentes si no introduce nuevos miembros de tipo [abstract](../../csharp/language-reference/keywords/abstract.md) ni cambia la semántica o el comportamiento de los tipos existentes. Por ejemplo, en .NET Framework 2.0, la clase <xref:System.Data.Common.DbConnection> se ha convertido en una nueva clase base para <xref:System.Data.SqlClient.SqlConnection>, que anteriormente había derivado directamente de <xref:System.ComponentModel.Component>.

- **✔️ Traslado de un tipo de un ensamblado a otro**

  Tenga en cuenta que el ensamblado *anterior* debe estar marcado con <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> que indica el nuevo ensamblado.

- **✔️ Cambio de un tipo [struct](../../csharp/language-reference/keywords/struct.md) a un tipo `readonly struct`**

  Tenga en cuenta que no se permite cambiar un tipo `readonly struct` a un tipo `struct`.

- **✔️ Adición de la palabra clave [sealed](../../csharp/language-reference/keywords/sealed.md) o [abstract](../../csharp/language-reference/keywords/abstract.md) a un tipo cuando hay ningún constructor *accesible* (público o protegido)**

- **✔️ Expansión de la visibilidad de un tipo**

- **❌ Cambio del espacio de nombres o del nombre de un tipo**

- **❌ Cambio de nombre o eliminación de un tipo público**

   Esto interrumpe todo el código que utiliza el tipo cuyo nombre se ha cambiado o quitado.

- **❌ Cambio del tipo subyacente de una enumeración**

   Se trata de un cambio importante en tiempo de compilación y de comportamiento, así como de un cambio importante binario que puede hacer que los argumentos de atributos no se puedan analizar.

- **❌ Sellado de un tipo anteriormente no estaba sellado**

- **❌ Adición de una interfaz al conjunto de tipos base de una interfaz**

   Si una interfaz implementa una interfaz que antes no se implementaba, todos los tipos que implementaron la versión original de la interfaz se interrumpen.

- **❓ Eliminación de una clase del conjunto de clases base o una interfaz desde el conjunto de interfaces implementadas**

  Hay una excepción a la regla para la eliminación de interfaces: puede agregar la implementación de una interfaz que se derive de la interfaz eliminada. Por ejemplo, puede quitar <xref:System.IDisposable> si el tipo o interfaz ahora implementa <xref:System.ComponentModel.IComponent>, que implementa <xref:System.IDisposable>.

- **❌ Cambio de un tipo `readonly struct` a un tipo [struct](../../csharp/language-reference/keywords/struct.md)**

  Tenga en cuenta que se permite el cambio de un tipo `struct` a un tipo `readonly struct`.

- **❌ Cambio de un tipo [struct](../../csharp/language-reference/keywords/struct.md) a un tipo `ref struct` y viceversa**

- **❌ Reducción de la visibilidad de un tipo**

   Sin embargo, se permite aumentar la visibilidad de un tipo.

### <a name="members"></a>Miembros

- **✔️ Expansión de la visibilidad de un miembro que no es [virtual](../../csharp/language-reference/keywords/sealed.md)**

- **✔️ Adición de un miembro de tipo abstract a un tipo público que no tiene ningún constructor *accesible* (público o protegido) o el tipo [sealed](../../csharp/language-reference/keywords/sealed.md)**

  Sin embargo, no se permite agregar un miembro de tipo abstract a un tipo que tenga constructores accesibles (públicos o protegidos) y que no sea `sealed`.

- **✔️ Restricción de la visibilidad de un miembro [protegido](../../csharp/language-reference/keywords/protected.md) cuando el tipo no tiene constructores accesibles (públicos o protegidos) o el tipo es [sellado](../../csharp/language-reference/keywords/sealed.md)** .

- **✔️ Desplazamiento de un miembro a una clase superior en la jerarquía que el tipo del que fue eliminado**

- **✔️ Adición o eliminación de una invalidación**

  Tenga en cuenta que la introducción de una invalidación puede hacer que los consumidores anteriores omitan la invalidación cuando llamen a la [base](../../csharp/language-reference/keywords/base.md).

- **✔️ Adición de un constructor a una clase, junto con un constructor sin parámetros si la clase no tenía previamente constructores**

   Sin embargo, no se permite agregar un constructor a una clase que antes no tenía constructores *sin* agregar el constructor sin parámetros.

- **✔️ Cambio de un miembro de tipo [abstract](../../csharp/language-reference/keywords/abstract.md) a [virtual](../../csharp/language-reference/keywords/virtual.md)**

- **✔️ Cambio de un valor devuelto `ref readonly` a un `ref` (excepto para los métodos o interfaces virtuales)**

- **✔️ Eliminación de [readonly](../../csharp/language-reference/keywords/readonly.md) desde un campo, a menos que el tipo estático del campo es un tipo de valor mutable**

- **✔️ Llamada a un nuevo evento que no se ha definido anteriormente**

- **❓ Adición de un nuevo campo de instancia a un tipo**

   Este cambio afecta a la serialización.

- **❌ Cambio de nombre o eliminación de un miembro o parámetro público**

   Esto interrumpe todo el código que utiliza el miembro o parámetro cuyo nombre se ha cambiado o quitado.

   Tenga en cuenta que esto incluye el cambio de nombre o eliminación de un captador o establecedor de una propiedad, así como el cambio de nombre o eliminación de los miembros de la enumeración.

- **❌ Adición de un miembro a una interfaz**

- **❌ Cambio del valor de un miembro constante o de enumeración público**

- **❌ Cambio del tipo de una propiedad, campo, parámetro o valor devuelto**

- **❌ Adición, eliminación o cambio del orden de los parámetros**

- **❌ Adición o eliminación de la palabra clave [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) o [ref](../../csharp/language-reference/keywords/ref.md) en un parámetro**

- **❌ Cambio de nombre de un parámetro (incluido el cambio de mayúsculas y minúsculas)**

  Esto se considera importante por dos motivos:

  - Interrumpe los escenarios de enlace en tiempo de ejecución, como la característica de enlace en tiempo de ejecución en Visual Basic y [dinámica](../../csharp/language-reference/builtin-types/reference-types.md#the-dynamic-type) en C#.

  - Interrumpe la [compatibilidad del origen](categories.md#source-compatibility) cuando los desarrolladores utilizan los [argumentos con nombre](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments).

- **❌ Cambio de un valor `ref` devuelto a un valor `ref readonly` devuelto**

- **❌ Cambio de un valor `ref readonly` devuelto a un valor `ref` en una interfaz o método virtual**

- **❌ Adición o eliminación del tipo [abstract](../../csharp/language-reference/keywords/abstract.md) de un miembro**

- **❌ Eliminación de la palabra clave [virtual](../../csharp/language-reference/keywords/virtual.md) de un miembro**

  Aunque esto a menudo no es un cambio importante porque el compilador de C# tiende a emitir las instrucciones de lenguaje intermedio (IL) [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) para llamar a métodos no virtuales (`callvirt` realiza una comprobación nula, mientras que una llamada normal no lo hace), este comportamiento no es invariable por varias razones:
  - C# no es el único lenguaje al que se dirige .NET.

  - El compilador de C# intenta cada vez más optimizar `callvirt` para una llamada normal cuando el método de destino no es virtual y probablemente no es nulo (como un método al que se accede a través del operador de propagación nula [?](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)).

  Convertir un método en virtual significa que el código del consumidor a menudo acabaría llamándolo no virtual.

- **❌ Adición de la palabra clave [virtual](../../csharp/language-reference/keywords/virtual.md) a un miembro**

- **❌ Conversión de un miembro virtual en tipo abstract**

  Un [miembro virtual](../../csharp/language-reference/keywords/virtual.md) proporciona una implementación del método que *se puede* reemplazar por una clase derivada. Un [miembro abstract](../../csharp/language-reference/keywords/abstract.md) no proporciona ninguna implementación y *debe ser* reemplazado.

- **❌ Adición de un miembro de tipo abstract a un tipo público que tiene constructores accesibles (públicos o protegidos) y que no es de tipo [sealed](../../csharp/language-reference/keywords/sealed.md)**

- **❌ Adición y eliminación de la palabra clave [static](../../csharp/language-reference/keywords/static.md) de un miembro**

- **❌ Adición de una sobrecarga que impide una sobrecarga existente y define un comportamiento diferente**

  Esto interrumpe a los clientes existentes que se enlazaron a la sobrecarga anterior. Por ejemplo, si una clase tiene una versión única de un método que acepta un <xref:System.UInt32>, un consumidor existente se enlazará correctamente a esa sobrecarga al pasar un valor <xref:System.Int32>. Sin embargo, si agrega una sobrecarga que acepte un <xref:System.Int32>, al volver a compilar o utilizar la característica de enlace en tiempo de ejecución, el compilador se enlaza ahora a la nueva sobrecarga. Si se produce un comportamiento diferente, se trata de un cambio importante.

- **❌ Adición de un constructor a una clase que antes no tenía constructores sin agregar el constructor sin parámetros**

- **❌ Adición de [readonly](../../csharp/language-reference/keywords/readonly.md) a un campo**

- **❌ Reducción de la visibilidad de un miembro**

   Esto incluye la reducción de la visibilidad de un miembro [protegido](../../csharp/language-reference/keywords/protected.md) cuando hay constructores *accesibles* (públicos o protegidos) y el tipo *no* es de tipo [sealed](../../csharp/language-reference/keywords/sealed.md). Si no es así, se permite reducir la visibilidad de un miembro protegido.

   Tenga en cuenta que se permite aumentar la visibilidad de un miembro.

- **❌ Cambio del tipo de un miembro**

   El valor devuelto de un método o el tipo de propiedad o campo no se pueden modificar. Por ejemplo, la firma de un método que devuelve un <xref:System.Object> no se puede cambiar para devolver un <xref:System.String>, o viceversa.

- **❌ Adición de un campo a una estructura que previamente no tenía ningún estado**

  Las reglas de asignación definidas permiten el uso de variables no inicializadas siempre que el tipo de variable sea una estructura sin estado. Si la estructura se realiza con estado, el código podría acabar con datos sin inicializar. Esto es a la vez una posible interrupción del origen y un cambio importante de archivo binario.

- **❌ Desencadenamiento de un evento existente que nunca se desencadenó antes**

## <a name="behavioral-changes"></a>Cambios de comportamiento

### <a name="assemblies"></a>Ensamblados

- **✔️ Portabilidad de un ensamblado cuando se siguen admitiendo las mismas plataformas**

- **❌ Cambio de nombre de un ensamblado**
- **❌ Cambio de la clave pública de un ensamblado**

### <a name="properties-fields-parameters-and-return-values"></a>Propiedades, campos, parámetros y valores devueltos

- **✔️ Cambio del valor de una propiedad, un campo, un valor devuelto o del parámetro [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) a un tipo más derivado**

  Por ejemplo, un método que devuelve un tipo de <xref:System.Object> puede devolver una instancia de <xref:System.String>. (Sin embargo, no se puede cambiar la firma del método).

- **✔️ Aumento del intervalo de valores aceptados para una propiedad o parámetro si el miembro no es [virtual](../../csharp/language-reference/keywords/virtual.md)**

  Tenga en cuenta que mientras que el rango de valores que se pueden pasar al método o que se devuelven por el miembro puede expandirse, el parámetro o tipo de miembro no pueden. Por ejemplo, mientras que los valores pasados a un método pueden expandirse de 0-124 a 0-255, el tipo de parámetro no puede cambiar de <xref:System.Byte> a <xref:System.Int32>.

- **❌ Aumento del intervalo de valores aceptados para una propiedad o parámetro si el miembro es [virtual](../../csharp/language-reference/keywords/virtual.md)**

   Este cambio interrumpe los miembros invalidados existentes, que no funcionarán correctamente para la gama extendida de valores.

- **❌ Disminución del intervalo de valores aceptados para una propiedad o parámetro**

- **❌ Aumento del intervalo de valores devueltos para una propiedad, un campo, un valor devuelto o el parámetro [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)**

- **❌ Cambio de los valores devueltos para una propiedad, un campo, un valor devuelto del método o el parámetro [out](../../csharp/language-reference/keywords/out-parameter-modifier.md)**

- **❌ Cambio del valor predeterminado de una propiedad, un campo o un parámetro**

- **❌ Cambio de la precisión de un valor devuelto numérico**

- **❓ Un cambio en el análisis de la entrada y el inicio de nuevas excepciones (incluso si el comportamiento de análisis no está especificado en la documentación)**

### <a name="exceptions"></a>Excepciones

- **✔️ Inicio de una excepción más derivada que una excepción existente**

  Debido a que la nueva excepción es una subclase de una excepción existente, el código de tratamiento de excepciones anterior continúa controlando la excepción. Por ejemplo, en .NET Framework 4, los métodos de creación y recuperación de la referencia cultural comenzaron a iniciar un <xref:System.Globalization.CultureNotFoundException> en lugar de un <xref:System.ArgumentException> si no se podía encontrar la referencia cultural. Dado que <xref:System.Globalization.CultureNotFoundException> procede de <xref:System.ArgumentException>, se trata de un cambio aceptable.

- **✔️ Inicio de una excepción más específica que <xref:System.NotSupportedException>, <xref:System.NotImplementedException>, <xref:System.NullReferenceException>**

- **✔️ Inicio de una excepción que se considera irrecuperable**

  Las excepciones irrecuperables no deben capturarse, sino que deben tratarse por un controlador general de alto nivel. Por lo tanto, no se espera que los usuarios tengan un código que capte estas excepciones explícitas. Las excepciones irrecuperables son:

  - <xref:System.AccessViolationException>
  - <xref:System.ExecutionEngineException>
  - <xref:System.Runtime.InteropServices.SEHException>
  - <xref:System.StackOverflowException>

- **✔️ Inicio de una nueva excepción en una nueva ruta de acceso del código**

  La excepción debe aplicarse solo a una nueva ruta de acceso del código que se ejecute con nuevos valores o estados de parámetros, y que no se pueda ejecutar por código existente que apunte a la versión anterior.

- **✔️ Eliminación de una excepción para permitir un comportamiento más sólido o nuevos escenarios**

  Por ejemplo, un método `Divide` que anteriormente solo trataba valores positivos e iniciaba un <xref:System.ArgumentOutOfRangeException> de lo contrario, puede cambiarse para admitir tanto valores negativos como positivos sin iniciar una excepción.

- **✔️ Cambio del texto de un mensaje de error**

  Los desarrolladores no deben confiar en el texto de los mensajes de error, que también cambian en función de la referencia cultural del usuario.

- **❌ Inicio de una excepción en cualquier otro caso no enumerado anteriormente**

- **❌ Eliminación de una excepción en cualquier otro caso no enumerado anteriormente**

### <a name="attributes"></a>Atributos

- **✔️ Cambio del valor de un atributo que *no* es observable**

- **❌ Cambio del valor de un atributo que *es* observable**

- **❓ Eliminación de un atributo**

  En la mayoría de los casos, la eliminación de un atributo (como <xref:System.NonSerializedAttribute>) es un cambio importante.

## <a name="platform-support"></a>Compatibilidad con la plataforma

- **✔️ Admisión de una operación en una plataforma que antes no era posible**

- **❌ No admitir o requerir ahora un Service Pack específico para una operación que antes estaba admitida en una plataforma.**

## <a name="internal-implementation-changes"></a>Cambios de implementación internos

- **❓ Cambio del área expuesta de un tipo interno**

   Por lo general se permiten estos cambios, aunque interrumpan la reflexión privada. En algunos casos, cuando las bibliotecas populares de terceros o un gran número de desarrolladores dependen de las API internas, es posible que no se permitan dichos cambios.

- **❓ Cambio de la implementación interna de un miembro**

  Por lo general se permiten estos cambios, aunque interrumpan la reflexión privada. En algunos casos, cuando el código del cliente depende con frecuencia de una reflexión privada o cuando el cambio introduce efectos secundarios no deseados, estos cambios pueden no estar permitidos.

- **✔️ Mejora del rendimiento de una operación**

   La capacidad de modificar el rendimiento de una operación es esencial, pero tales cambios pueden interrumpir el código que depende de la velocidad actual de una operación. Esto es particularmente cierto en el caso del código que depende de la sincronización de las operaciones asincrónicas. Tenga en cuenta que el cambio en el rendimiento no debería tener ningún efecto en otro comportamiento de la API en cuestión; de lo contrario, el cambio se considerará importante.

- **✔️ Modificación indirecta (y a menudo de forma adversa) del rendimiento de una operación**

  Si el cambio en cuestión no está clasificado como importante por algún otro motivo, esto es aceptable. A menudo, es necesario tomar medidas que pueden incluir operaciones adicionales o que agregan nueva funcionalidad. Esto casi siempre afectará al rendimiento, pero puede ser esencial para que la API en cuestión funcione como se esperaba.

- **❌ Cambio de una API sincrónica en asincrónica (y viceversa)**

## <a name="code-changes"></a>Cambios en el código

- **✔️ Adición de [params](../../csharp/language-reference/keywords/params.md) a un parámetro**

- **❌ Cambio de un tipo [struct](../../csharp/language-reference/keywords/struct.md) a un tipo [class](../../csharp/language-reference/keywords/class.md) y viceversa**

- **❌ Adición de la palabra clave [checked](../../csharp/language-reference/keywords/virtual.md) a un bloque de código**

   Este cambio puede causar que el código que se ejecutó previamente inicie un <xref:System.OverflowException> y es inaceptable.

- **❌ Eliminación de [params](../../csharp/language-reference/keywords/params.md) de un parámetro**

- **❌ Cambio del orden en el que se desencadenan los eventos**

  Los desarrolladores pueden esperar razonablemente que los eventos se desencadenen en el mismo orden, y el código de desarrollador depende frecuentemente del orden en el que se desencadenen los eventos.

- **❌ Eliminación del inicio de un evento en una acción determinada**

- **❌ Cambio del número de veces que se llaman los eventos dados**

- **❌ Adición de <xref:System.FlagsAttribute> a un tipo de enumeración**
