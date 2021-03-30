---
title: 'Uso de tipos de registros: tutorial de C#'
description: Obtenga información sobre cómo usar tipos de registros, compilar jerarquías de registros y cuándo elegir registros en lugar de clases.
ms.date: 11/12/2020
ms.openlocfilehash: 301eaf1ddf6d6b7dc1f88ffa4c790e2c2b01862f
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104878963"
---
# <a name="create-record-types"></a>Creación de tipos de registros

C# 9 incorpora *registros*, un nuevo tipo de referencia que se puede crear en lugar de clases o structs. Los registros se diferencian de las clases en que los tipos de registros usan *igualdad basada en valores*. Dos variables de un tipo de registro son iguales si las definiciones del tipo de registro son idénticas y si, en cada campo, los valores de ambos registros son iguales. Dos variables de un tipo de clase son iguales si los objetos a los que se hace referencia son el mismo tipo de clase y las variables hacen referencia al mismo objeto. La igualdad basada en valores conlleva otras capacidades que probablemente quiera en los tipos de registros. El compilador genera muchos de esos miembros al declarar un elemento `record` en lugar de `class`.

En este tutorial, aprenderá a:

> [!div class="checklist"]
>
> - Decidir si debe declarar un elemento `class` o `record`.
> - Declarar tipos de registros y tipos de registros posicionales.
> - Reemplazar los métodos por métodos generados por el compilador en los registros.

## <a name="prerequisites"></a>Prerrequisitos

Tiene que configurar la máquina para ejecutar .NET 5 o posterior, incluido el compilador de C# 9.0 o posterior. El compilador de C# 9.0 está disponible a partir de la [versión 16.8 de Visual Studio 2019](https://visualstudio.microsoft.com/vs) o del [SDK de .NET 5.0](https://dotnet.microsoft.com/download).

## <a name="characteristics-of-records"></a>Características de los registros

Un *registro* se define al declarar un tipo con la palabra clave `record` en lugar de `class` o `struct`. Un registro es un tipo de referencia y sigue la semántica de la igualdad basada en valores. Para aplicar la semántica de valores, el compilador genera varios métodos para el tipo de registro:

- Una invalidación de <xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>.
- Un método `Equals` virtual cuyo parámetro es el tipo de registro.
- Una invalidación de <xref:System.Object.GetHashCode?displayProperty=nameWithType>.
- Métodos para `operator ==` y `operator !=`.
- Los tipos de registros implementan <xref:System.IEquatable%601?displayProperty=nameWithType>.

Además, los registros proporcionan una invalidación de <xref:System.Object.ToString?displayProperty=nameWithType>. El compilador sintetiza métodos para mostrar registros mediante <xref:System.Object.ToString?displayProperty=nameWithType>. Va a examinar esos miembros a medida que escribe el código de este tutorial. Los registros admiten expresiones `with` para habilitar la mutación no destructiva de registros.

También puede declarar *registros posicionales* mediante una sintaxis más concisa. El compilador sintetiza más métodos automáticamente cuando se declaran registros posicionales:

- Un constructor primario cuyos parámetros coinciden con los parámetros posicionales en la declaración del registro.
- Propiedades públicas init-only para cada parámetro de un constructor primario.
- Un método `Deconstruct` para extraer propiedades del registro.

## <a name="build-temperature-data"></a>Compilación de datos de temperatura

Los datos y las estadísticas se encuentran entre los escenarios en los que se recomienda usar registros. En este tutorial va a compilar una aplicación que calcula *grados día* para distintos usos. Los *grados día* son una medida de calor (o falta de él) a lo largo de un período de días, semanas o meses. Los grados día realizan un seguimiento del uso energético y lo predicen. Más días más cálidos significan más aire acondicionado, mientras que más días más fríos implican un mayor uso de calefacción. Los grados día resultan útiles para administrar la población vegetal y poner en correlación su crecimiento a medida que cambiamos de estación. Los grados día ayudan a realizar un seguimiento de las migraciones animales de especies que se desplazan según el clima.

La fórmula se basa en la temperatura media de un día determinado y una temperatura de base de referencia. Para calcular los grados día a lo largo del tiempo, necesita la temperatura mínima y máxima de cada día durante un período de tiempo. Comencemos por crear una nueva aplicación. Cree una nueva aplicación de consola. Cree un nuevo tipo de registro en un nuevo archivo denominado "DailyTemperature.cs":

:::code language="csharp" source="snippets/record-types/InterimSteps.cs" ID="DailyRecord":::

El código anterior define un *registro posicional*. Ha creado un tipo de referencia que contiene dos propiedades: `HighTemp` y `LowTemp`. Esas propiedades son *propiedades init-only*, lo que significa que se pueden establecer en el constructor o mediante un inicializador de propiedad. El tipo `DailyTemperature` también tiene un *constructor primario* con dos parámetros que coinciden con las dos propiedades. Use el constructor primario para inicializar un registro `DailyTemperature`:

:::code language="csharp" source="snippets/record-types/Program.cs" ID="DeclareData":::

Puede agregar sus propias propiedades o métodos a los registros, incluidos los registros posicionales. Tiene que calcular la temperatura media de cada día. Puede agregar esa propiedad al registro `DailyTemperature`:

:::code language="csharp" source="snippets/record-types/DailyTemperature.cs" ID="TemperatureRecord":::

Vamos a asegurarnos de que puede usar estos datos. Agregue el código siguiente al método `Main`:

```csharp
foreach (var item in data)
    Console.WriteLine(item);
```

Ejecute la aplicación y verá un resultado similar a la siguiente pantalla (se han quitado varias filas por motivos de espacio):

```dotnetcli
DailyTemperature { HighTemp = 57, LowTemp = 30, Mean = 43.5 }
DailyTemperature { HighTemp = 60, LowTemp = 35, Mean = 47.5 }


DailyTemperature { HighTemp = 80, LowTemp = 60, Mean = 70 }
DailyTemperature { HighTemp = 85, LowTemp = 66, Mean = 75.5 }
```

El código anterior muestra el resultado de la invalidación de `ToString` sintetizada por el compilador. Si prefiere otro texto, puede escribir una versión propia de `ToString` que impida al compilador sintetizar otra para el usuario.

## <a name="compute-degree-days"></a>Cálculo de grados día

Para calcular los grados día, tome la diferencia entre una temperatura de base de referencia y la temperatura media de un día determinado. Para medir el calor a lo largo del tiempo, descarte todos los días en los que la temperatura media esté por debajo de la base de referencia. Para medir el frío a lo largo del tiempo, descarte todos los días en los que la temperatura media esté por encima de la base de referencia. Por ejemplo, en EE. UU. se usa 65F como base de los grados día de calefacción y refrigeración. Esa es la temperatura a la que no se necesita calefacción ni refrigeración. Si un día tiene una temperatura media de 70F, ese día es 5 grados día de refrigeración y 0 grados día de calefacción. A la inversa, si la temperatura media es de 55F, ese día es 10 grados día de calefacción y 0 grados día de refrigeración.

Estas fórmulas se pueden expresar como una pequeña jerarquía de tipos de registros: un tipo de grado día abstracto y dos tipos concretos de grados días de calefacción y grados día de refrigeración. Estos tipos también pueden ser registros posicionales. Toman una temperatura de base de referencia y una secuencia de registros de temperatura diaria como argumentos del constructor primario:

:::code language="csharp" source="snippets/record-types/InterimSteps.cs" ID="DegreeDaysRecords":::

El registro `DegreeDays` abstracto es la clase base compartida de los registros `HeatingDegreeDays` y `CoolingDegreeDays`. Las declaraciones del constructor primario en los registros derivados muestran cómo administrar la inicialización de registros base. El registro derivado declara parámetros para todos los parámetros del constructor primario del registro base. El registro base declara e inicializa esas propiedades. El registro derivado no las oculta, sino que solo crea e inicializa propiedades para los parámetros que no se han declarado en su registro base. En este ejemplo, los registros derivados no agregan nuevos parámetros del constructor primario. Pruebe el código mediante la adición del código siguiente a su método `Main`:

:::code language="csharp" source="snippets/record-types/Program.cs" ID="HeatingAndCooling":::

Se obtiene un resultado similar a la siguiente pantalla:

```dotnetcli
HeatingDegreeDays { BaseTemperature = 65, TempRecords = record_types.DailyTemperature[], DegreeDays = 85 }
CoolingDegreeDays { BaseTemperature = 65, TempRecords = record_types.DailyTemperature[], DegreeDays = 71.5 }
```

## <a name="define-compiler-synthesized-methods"></a>Definición de métodos sintetizados por el compilador

El código calcula el número correcto de grados día de calefacción y refrigeración durante ese período de tiempo. Pero en este ejemplo se muestra por qué es recomendable reemplazar algunos de los métodos sintetizados por registros. Puede declarar su propia versión de cualquiera de los métodos sintetizados por el compilador en un tipo de registro, excepto el método Clone. El método Clone tiene un nombre generado por el compilador y no se puede proporcionar otra implementación. Estos métodos sintetizados incluyen un constructor de copias, los miembros de la interfaz <xref:System.IEquatable%601?displayProperty=nameWithType>, las pruebas de igualdad y desigualdad y <xref:System.Object.GetHashCode>. Para los fines de este artículo, se va a sintetizar `PrintMembers`. También puede declarar su propio elemento `ToString`, pero `PrintMembers` constituye una mejor opción para los escenarios de herencia. Para proporcionar su propia versión de un método sintetizado, la firma debe coincidir con el método sintetizado.

El elemento `TempRecords` del resultado de la consola no es útil. Muestra el tipo, pero nada más. Puede cambiar este comportamiento si proporciona su propia implementación del método sintetizado `PrintMembers`. La firma depende de los modificadores aplicados a la declaración de `record`:

- Si un tipo de registro es `sealed`, la firma es `private bool PrintMembers(StringBuilder builder);`
- Si un tipo de registro no es `sealed` y deriva de `object` (es decir, no declara un registro base), la firma es `protected virtual bool PrintMembers(StringBuilder builder);`
- Si un tipo de registro no es `sealed` y deriva de otro registro, la firma es `protected override bool PrintMembers(StringBuilder builder);`

Estas reglas son más fáciles de asimilar si se entiende el propósito de `PrintMembers`. `PrintMembers` agrega información sobre cada propiedad de un tipo de registro a una cadena. El contrato requiere que los registros base agreguen sus miembros a la pantalla y da por hecho que los miembros derivados van a agregar sus miembros. Cada tipo de registro sintetiza una invalidación de `ToString` que es similar al ejemplo siguiente de `HeatingDegreeDays`:

```csharp
public override string ToString()
{
    StringBuilder stringBuilder = new StringBuilder();
    stringBuilder.Append("HeatingDegreeDays");
    stringBuilder.Append(" { ");
    if (PrintMembers(stringBuilder))
    {
        stringBuilder.Append(" ");
    }
    stringBuilder.Append("}");
    return stringBuilder.ToString();
}
```

Declare un método `PrintMembers` en el registro `DegreeDays` que no imprima el tipo de la colección:

:::code language="csharp" source="snippets/record-types/DegreeDays.cs" ID="AddPrintMembers":::

La firma declara un método `virtual protected` para que coincida con la versión del compilador. No se preocupe si obtiene los descriptores de acceso incorrectos; el lenguaje aplica la firma correcta. Si olvida los modificadores correctos de cualquier método sintetizado, el compilador emite advertencias o errores que ayudan a obtener la firma correcta.

## <a name="non-destructive-mutation"></a>Mutación no destructiva

Los miembros sintetizados de un registro posicional no modifican el estado del registro. El objetivo es que se puedan crear registros inmutables más fácilmente. Vuelva a observar las declaraciones anteriores de `HeatingDegreeDays` y `CoolingDegreeDays`. Los miembros agregados realizan cálculos en los valores del registro, pero no mutan el estado. Los registros posicionales facilitan la creación de tipos de referencia inmutables.

La creación de tipos de referencia inmutables significa que se recomienda usar la mutación no destructiva. Cree nuevas instancias de registro que sean similares a las instancias de registro existentes mediante [expresiones `with`](../../language-reference/operators/with-expression.md). Estas expresiones son una construcción de copia con asignaciones adicionales que modifican la copia. El resultado es una nueva instancia de registro en la que se ha copiado cada propiedad del registro existente y, opcionalmente, se ha modificado. El registro original no se ha modificado.

Vamos a agregar un par de características al programa que muestren expresiones `with`. En primer lugar, vamos a crear un nuevo registro para calcular la suma térmica con los mismos datos. La *suma térmica* suele usar 41F como base de referencia y mide las temperaturas por encima de ella. Para usar los mismos datos, puede crear un nuevo registro similar a `coolingDegreeDays`, pero con otra temperatura base:

:::code language="csharp" source="snippets/record-types/Program.cs" ID="GrowingDegreeDays":::

Puede comparar el número de grados calculado con los números generados con una temperatura de base de referencia superior. Recuerde que los registros son *tipos de referencia* y estas copias son instantáneas. No se copia la matriz de los datos, sino que ambos registros hacen referencia a los mismos datos. Ese hecho supone una ventaja en otro escenario. En el caso de la suma térmica, es útil realizar un seguimiento del total de los cinco días anteriores. Puede crear nuevos registros con otros datos de origen mediante expresiones `with`. En el código siguiente se compila una colección de estas acumulaciones y luego se muestran los valores:

:::code language="csharp" source="snippets/record-types/Program.cs" ID="RunningFiveDayTotal":::

También puede usar expresiones `with` para crear copias de registros. No especifique ninguna propiedad entre las llaves de la expresión `with`. Eso significa crear una copia y no cambiar ninguna propiedad:

```csharp
var growingDegreeDaysCopy = growingDegreeDays with { };
```

Ejecute la aplicación terminada para ver los resultados.

## <a name="summary"></a>Resumen

En este tutorial se han mostrado varios aspectos de los registros. Los registros proporcionan una sintaxis concisa para los tipos de referencia cuyo uso fundamental es el almacenamiento de datos. En el caso de las clases orientadas a objetos, el uso fundamental es definir responsabilidades. Este tutorial se ha centrado en los *registros posicionales*, donde se puede usar una sintaxis concisa para declarar las propiedades init-only de un registro. El compilador sintetiza varios miembros del registro para copiar y comparar registros. Puede agregar cualquier otro miembro que necesite para sus tipos de registros. Puede crear tipos de registros inmutables sabiendo que ninguno de los miembros generados por el compilador mutaría su estado. Además, las expresiones `with` facilitan la compatibilidad con la mutación no destructiva.

Los registros presentan otra manera de definir tipos. Se usan definiciones `class` para crear jerarquías orientadas a objetos que se centran en las responsabilidades y el comportamiento de los objetos. Cree tipos `struct` para las estructuras de datos que almacenan datos y que son lo suficientemente pequeñas como para copiarse de forma eficaz. Cree tipos `record` si lo que busca son comparaciones y análisis de similitud que se basen en valores, y quiere usar variables de referencia, pero no copiar valores.

Puede obtener una descripción completa de los registros en el [artículo de referencia del lenguaje C# para el tipo de registro](../../language-reference/builtin-types/record.md) y la [especificación de tipo de registro propuesta](~/_csharplang/proposals/csharp-9.0/records.md).
