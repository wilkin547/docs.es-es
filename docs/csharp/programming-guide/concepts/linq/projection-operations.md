---
title: Operaciones de proyección (C#)
ms.date: 07/20/2015
ms.assetid: 98df573a-aad9-4b8c-9a71-844be2c4fb41
ms.openlocfilehash: f76eeeb779ab08a575e758a9d974573b700ae652
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168341"
---
# <a name="projection-operations-c"></a>Operaciones de proyección (C#)
El término "proyección" hace referencia a la operación de transformar un objeto en una nueva forma que, a menudo, consta solo de aquellas propiedades que se usarán posteriormente. Utilizando la proyección, puede construir un tipo nuevo creado a partir de cada objeto. Se puede proyectar una propiedad y realizar una función matemática en ella. También puede proyectar el objeto original sin cambiarlo.  
  
 Los métodos del operador de consulta estándar que realizan proyecciones se indican en la sección siguiente.  
  
## <a name="methods"></a>Métodos  
  
|Nombre del método|Description|Sintaxis de la expresión de consulta de C#|Más información|  
|-----------------|-----------------|---------------------------------|----------------------|  
|Seleccionar|Proyecta valores basados en una función de transformación.|`select`|<xref:System.Linq.Enumerable.Select%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Select%2A?displayProperty=nameWithType>|  
|SelectMany|Proyecta secuencias de valores que se basan en una función de transformación y después los convierte en una secuencia.|Use varias cláusulas `from`|<xref:System.Linq.Enumerable.SelectMany%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.SelectMany%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a>Ejemplos de sintaxis de expresiones de consulta  
  
### <a name="select"></a>Seleccionar  
 En el ejemplo siguiente se usa la cláusula `select` para proyectar la primera letra de cada cadena de una lista de cadenas.  
  
```csharp  
List<string> words = new List<string>() { "an", "apple", "a", "day" };  
  
var query = from word in words  
            select word.Substring(0, 1);  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    a  
    a  
    a  
    d  
*/  
```  
  
### <a name="selectmany"></a>SelectMany  
 En el ejemplo siguiente se usan varias cláusulas `from` para proyectar cada palabra de todas las cadenas de una lista de cadenas.  
  
```csharp  
List<string> phrases = new List<string>() { "an apple a day", "the quick brown fox" };  
  
var query = from phrase in phrases  
            from word in phrase.Split(' ')  
            select word;  
  
foreach (string s in query)  
    Console.WriteLine(s);  
  
/* This code produces the following output:  
  
    an  
    apple  
    a  
    day  
    the  
    quick  
    brown  
    fox  
*/  
```  
  
## <a name="select-versus-selectmany"></a>Select frente a SelectMany  
 La función tanto de `Select()` como de `SelectMany()` consiste en generar un valor (o valores) de resultado a partir de valores de origen. `Select()` genera un valor de resultado para cada valor de origen. El resultado global, por tanto, es una colección que tiene el mismo número de elementos que la colección de origen. En cambio, `SelectMany()` genera un resultado global único que contiene subcolecciones concatenadas procedentes de cada valor de origen. La función de transformación que se pasa como argumento a `SelectMany()` debe devolver una secuencia enumerable de valores para cada valor de origen. Luego, `SelectMany()` concatena estas secuencias enumerables para crear una secuencia de gran tamaño.  
  
 Las dos ilustraciones siguientes muestran la diferencia conceptual entre las acciones de estos dos métodos. En cada caso, se supone que la función de selector (transformación) selecciona la matriz de flores de cada valor de origen.  
  
 En esta ilustración se muestra cómo `Select()` devuelve una colección que tiene el mismo número de elementos que la colección de origen.  
  
 ![Gráfico en el que se muestra la acción Select&#40;&#41;](./media/projection-operations/select-action-graphic.png)  
  
 En esta ilustración se muestra cómo `SelectMany()` concatena la secuencia intermedia de matrices en un valor de resultado final que contiene cada uno de los valores de todas las matrices intermedias.  
  
 ![Gráfico en el que se muestra la acción SelectMany&#40;&#41;.](./media/projection-operations/select-many-action-graphic.png )  
  
### <a name="code-example"></a>Ejemplo de código  
 En el ejemplo siguiente se compara el comportamiento de `Select()` y `SelectMany()`. El código crea un "ramo" de flores tomando los dos primeros elementos de cada lista de nombres de flores de la colección de origen. En este ejemplo, el "valor único" que la función de transformación <xref:System.Linq.Enumerable.Select%60%602%28System.Collections.Generic.IEnumerable%7B%60%600%7D%2CSystem.Func%7B%60%600%2C%60%601%7D%29> usa es una colección de valores. Para ello, se requiere el bucle adicional `foreach` a fin de enumerar cada una de las cadenas de cada subsecuencia.  
  
```csharp  
class Bouquet  
{  
    public List<string> Flowers { get; set; }  
}  
  
static void SelectVsSelectMany()  
{  
    List<Bouquet> bouquets = new List<Bouquet>() {  
        new Bouquet { Flowers = new List<string> { "sunflower", "daisy", "daffodil", "larkspur" }},  
        new Bouquet{ Flowers = new List<string> { "tulip", "rose", "orchid" }},  
        new Bouquet{ Flowers = new List<string> { "gladiolis", "lily", "snapdragon", "aster", "protea" }},  
        new Bouquet{ Flowers = new List<string> { "larkspur", "lilac", "iris", "dahlia" }}  
    };  
  
    // *********** Select ***********
    IEnumerable<List<string>> query1 = bouquets.Select(bq => bq.Flowers);  
  
    // ********* SelectMany *********  
    IEnumerable<string> query2 = bouquets.SelectMany(bq => bq.Flowers);  
  
    Console.WriteLine("Results by using Select():");  
    // Note the extra foreach loop here.  
    foreach (IEnumerable<String> collection in query1)  
        foreach (string item in collection)  
            Console.WriteLine(item);  
  
    Console.WriteLine("\nResults by using SelectMany():");  
    foreach (string item in query2)  
        Console.WriteLine(item);  
  
    /* This code produces the following output:  
  
       Results by using Select():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
  
       Results by using SelectMany():  
        sunflower  
        daisy  
        daffodil  
        larkspur  
        tulip  
        rose  
        orchid  
        gladiolis  
        lily  
        snapdragon  
        aster  
        protea  
        larkspur  
        lilac  
        iris  
        dahlia  
    */  
  
}  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Linq>
- [Standard Query Operators Overview (C#)](./standard-query-operators-overview.md)(Información general sobre operadores de consulta estándar (C#))
- [select (cláusula)](../../../language-reference/keywords/select-clause.md)
- [Procedimiento para rellenar colecciones de objetos de varios orígenes (LINQ) (C#)](./how-to-populate-object-collections-from-multiple-sources-linq.md)
- [Procedimiento para dividir un archivo en varios mediante el uso de grupos (LINQ) (C#)](./how-to-split-a-file-into-many-files-by-using-groups-linq.md)
