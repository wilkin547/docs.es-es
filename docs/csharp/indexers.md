---
title: Indizadores
description: Obtenga información sobre los indexadores de C# y cómo implementan propiedades indexadas, que son propiedades a las que se hace referencia con uno o más argumentos.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 0e9496da-e766-45a9-b92b-91820d4a350e
ms.openlocfilehash: e9b1cb18157982f068f1c1e4546e637f2bd707cb
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83394696"
---
# <a name="indexers"></a>Indizadores

Los *indizadores* son similares a las propiedades. Muchas veces, los indizadores se basan en las mismas características del lenguaje que las [propiedades](properties.md). Los indizadores permiten las propiedades *indizadas*: propiedades a las que se hace referencia mediante uno o más argumentos. Estos argumentos proporcionan un índice en alguna colección de valores.

## <a name="indexer-syntax"></a>Sintaxis del indizador

Se obtiene acceso a un indizador usando un nombre de variable y corchetes. Los argumentos del indizador se colocan dentro de los corchetes:

```csharp
var item = someObject["key"];
someObject["AnotherKey"] = item;
```

Los indizadores se declaran con la palabra clave `this` como nombre de la propiedad y declarando los argumentos entre corchetes. Esta declaración coincidiría con el uso que se muestra en el párrafo anterior:

```csharp
public int this[string key]
{
    get { return storage.Find(key); }
    set { storage.SetAt(key, value); }
}
```

En este ejemplo inicial puede ver la relación existente entre la sintaxis de las propiedades y los indizadores. Esta analogía lleva a cabo la mayoría de las reglas de sintaxis de los indizadores. Los indizadores pueden tener cualquier modificador de acceso válido (público, interno protegido, protegido, interno, privado o privado protegido). Pueden ser sellados, virtuales o abstractos. Al igual que con las propiedades, puede especificar distintos modificadores de acceso para los descriptores de acceso get y set en un indizador.
También puede especificar indizadores de solo lectura (omitiendo el descriptor de acceso set) o indizadores de solo escritura (omitiendo el descriptor de acceso get).

Puede aplicar a los indizadores casi todo lo que aprenda al trabajar con propiedades. La única excepción a esta regla son las *propiedades implementadas automáticamente*. El compilador no siempre puede generar el almacenamiento correcto para un indizador.

La presencia de argumentos para hacer referencia a un elemento en un conjunto de elementos distingue los indizadores de las propiedades. Puede definir varios indizadores en un tipo, mientras que las listas de argumentos de cada indizador son únicas. Vamos a explorar escenarios diferentes en los que puede usar uno o varios indizadores en una definición de clase.

## <a name="scenarios"></a>Escenarios

Tendría que definir *indizadores* en el tipo si su API modela alguna colección en la que se definen los argumentos de esa colección. Los indizadores pueden (o no) asignarse directamente a los tipos de colección que forman parte del marco de trabajo principal de .NET. El tipo puede tener otras responsabilidades, además de tener que modelar una colección.
Los indizadores le permiten proporcionar la API que coincida con la abstracción de su tipo sin tener que exponer la información interna de cómo se almacenan o se calculan los valores de dicha abstracción.

Veamos algunos de los escenarios habituales en los que se usan los *indizadores*. Puede obtener acceso a la [carpeta de ejemplo para indexadores](https://github.com/dotnet/samples/tree/master/csharp/indexers). Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../samples-and-tutorials/index.md#viewing-and-downloading-samples).

### <a name="arrays-and-vectors"></a>Matrices y vectores

Uno de los escenarios más comunes para crear indizadores es cuando el tipo modela una matriz o un vector. Puede crear un indizador para modelar una lista ordenada de datos.

La ventaja de crear su propio indizador es que puede definir el almacenamiento de esa colección para satisfacer sus necesidades. Piense en un escenario en el que el tipo modela datos históricos que tienen un tamaño demasiado grande para poder cargarlos en la memoria de una vez. Debe cargar y descargar secciones de la colección en función del uso. En el ejemplo siguiente se modela este comportamiento. Informa sobre el número de puntos de datos existente, crea páginas para incluir secciones de los datos a petición y quita páginas de la memoria para dejar espacio para las páginas necesarias para las solicitudes más recientes.

```csharp
public class DataSamples
{
    private class Page
    {
        private readonly List<Measurements> pageData = new List<Measurements>();
        private readonly int startingIndex;
        private readonly int length;
        private bool dirty;
        private DateTime lastAccess;

        public Page(int startingIndex, int length)
        {
            this.startingIndex = startingIndex;
            this.length = length;
            lastAccess = DateTime.Now;

            // This stays as random stuff:
            var generator = new Random();
            for(int i=0; i < length; i++)
            {
                var m = new Measurements
                {
                    HiTemp = generator.Next(50, 95),
                    LoTemp = generator.Next(12, 49),
                    AirPressure = 28.0 + generator.NextDouble() * 4
                };
                pageData.Add(m);
            }
        }
        public bool HasItem(int index) =>
            ((index >= startingIndex) &&
            (index < startingIndex + length));

        public Measurements this[int index]
        {
            get
            {
                lastAccess = DateTime.Now;
                return pageData[index - startingIndex];
            }
            set
            {
                pageData[index - startingIndex] = value;
                dirty = true;
                lastAccess = DateTime.Now;
            }
        }

        public bool Dirty => dirty;
        public DateTime LastAccess => lastAccess;
    }

    private readonly int totalSize;
    private readonly List<Page> pagesInMemory = new List<Page>();

    public DataSamples(int totalSize)
    {
        this.totalSize = totalSize;
    }

    public Measurements this[int index]
    {
        get
        {
            if (index < 0)
                throw new IndexOutOfRangeException("Cannot index less than 0");
            if (index >= totalSize)
                throw new IndexOutOfRangeException("Cannot index past the end of storage");

            var page = updateCachedPagesForAccess(index);
            return page[index];
        }
        set
        {
            if (index < 0)
                throw new IndexOutOfRangeException("Cannot index less than 0");
            if (index >= totalSize)
                throw new IndexOutOfRangeException("Cannot index past the end of storage");
            var page = updateCachedPagesForAccess(index);

            page[index] = value;
        }
    }

    private Page updateCachedPagesForAccess(int index)
    {
        foreach (var p in pagesInMemory)
        {
            if (p.HasItem(index))
            {
                return p;
            }
        }
        var startingIndex = (index / 1000) * 1000;
        var newPage = new Page(startingIndex, 1000);
        addPageToCache(newPage);
        return newPage;
    }

    private void addPageToCache(Page p)
    {
        if (pagesInMemory.Count > 4)
        {
            // remove oldest non-dirty page:
            var oldest = pagesInMemory
                .Where(page => !page.Dirty)
                .OrderBy(page => page.LastAccess)
                .FirstOrDefault();
            // Note that this may keep more than 5 pages in memory
            // if too much is dirty
            if (oldest != null)
                pagesInMemory.Remove(oldest);
        }
        pagesInMemory.Add(p);
    }
}
```

Puede seguir esta expresión de diseño para modelar cualquier tipo de colección cuando haya motivos de peso para no cargar todo el conjunto de datos en una colección en memoria. Observe que la clase `Page` es una clase anidada privada que no forma parte de la interfaz pública. Estos datos se ocultan a los usuarios de esta clase.

### <a name="dictionaries"></a>Diccionarios

Otro escenario habitual es cuando necesita modelar un diccionario o una asignación. En este escenario, el tipo almacena valores en función de la clave (normalmente claves de texto). En este ejemplo se crea un diccionario que asigna argumentos de la línea de comandos a [expresiones lambda](delegates-overview.md) que administran estas opciones. En el ejemplo siguiente se muestran dos clases: una clase `ArgsActions`, que asigna una opción de la línea de comandos a un delegado `Action`; y `ArgsProcessor`, que usa `ArgsActions` para ejecutar cada `Action` cuando encuentra esa opción.

```csharp
public class ArgsProcessor
{
    private readonly ArgsActions actions;

    public ArgsProcessor(ArgsActions actions)
    {
        this.actions = actions;
    }

    public void Process(string[] args)
    {
        foreach(var arg in args)
        {
            actions[arg]?.Invoke();
        }
    }

}
public class ArgsActions
{
    readonly private Dictionary<string, Action> argsActions = new Dictionary<string, Action>();

    public Action this[string s]
    {
        get
        {
            Action action;
            Action defaultAction = () => {} ;
            return argsActions.TryGetValue(s, out action) ? action : defaultAction;
        }
    }

    public void SetOption(string s, Action a)
    {
        argsActions[s] = a;
    }
}
```

En este ejemplo, la colección `ArgsAction` está estrechamente relacionada con la colección subyacente.
`get` determina si se ha configurado una opción determinada. Si es así, devuelve la `Action` asociada a esa opción. Si no, devuelve una `Action` que no hace nada. El descriptor de acceso público no incluye ningún descriptor de acceso `set`, sino el diseño que usa un método público para establecer opciones.

### <a name="multi-dimensional-maps"></a>Asignaciones multidimensionales

Puede crear indizadores que usen varios argumentos. Además, estos argumentos no se restringen para que sean del mismo tipo. Veamos dos ejemplos.

En el primer ejemplo se muestra una clase que genera valores para el conjunto Mandelbrot. Para obtener más información sobre las matemáticas subyacentes en el conjunto, lea [este artículo](https://en.wikipedia.org/wiki/Mandelbrot_set).
El indizador usa dos valores double para definir un punto en el plano X, Y.
El descriptor de acceso get calcula el número de iteraciones existente hasta que se determina que un punto no está en el conjunto. Si se alcanza el número máximo de iteraciones, el punto está en el conjunto y se devuelve el valor maxIterations de la clase (las imágenes generadas por PC popularizadas para el conjunto Mandelbrot definen colores para el número de iteraciones que son necesarias para determinar que un punto en concreto está fuera del conjunto).

```csharp
public class Mandelbrot
{
    readonly private int maxIterations;

    public Mandelbrot(int maxIterations)
    {
        this.maxIterations = maxIterations;
    }

    public int this [double x, double y]
    {
        get
        {
            var iterations = 0;
            var x0 = x;
            var y0 = y;

            while ((x*x + y * y < 4) &&
                (iterations < maxIterations))
            {
                var newX = x * x - y * y + x0;
                y = 2 * x * y + y0;
                x = newX;
                iterations++;
            }
            return iterations;
        }
    }
}
```

El conjunto Mandelbrot define valores en cada coordenada (x o y) para los valores numéricos reales.
Con esto se define un diccionario que puede contener un número infinito de valores. Por lo tanto, no hay ningún almacenamiento detrás del conjunto. En su lugar, esta clase calcula el valor de cada punto cuando el código llama al descriptor de acceso `get`, por lo que no se usa ningún almacenamiento subyacente.

Vamos a examinar un último uso de los indizadores, en el que el indizador toma varios argumentos de distintos tipos. Imagínese un programa que administra datos históricos de temperaturas. Este indizador usa una ciudad y una fecha para establecer u obtener las temperaturas máximas y mínimas de ese lugar:

```csharp
using DateMeasurements =
    System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>;
using CityDataMeasurements =
    System.Collections.Generic.Dictionary<string, System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>>;

public class HistoricalWeatherData
{
    readonly CityDataMeasurements storage = new CityDataMeasurements();

    public Measurements this[string city, DateTime date]
    {
        get
        {
            var cityData = default(DateMeasurements);

            if (!storage.TryGetValue(city, out cityData))
                throw new ArgumentOutOfRangeException(nameof(city), "City not found");

            // strip out any time portion:
            var index = date.Date;
            var measure = default(Measurements);
            if (cityData.TryGetValue(index, out measure))
                return measure;
            throw new ArgumentOutOfRangeException(nameof(date), "Date not found");
        }
        set
        {
            var cityData = default(DateMeasurements);

            if (!storage.TryGetValue(city, out cityData))
            {
                cityData = new DateMeasurements();
                storage.Add(city, cityData);
            }

            // Strip out any time portion:
            var index = date.Date;
            cityData[index] = value;
        }
    }
}
```

Este ejemplo crea un indizador que asigna los datos meteorológicos en dos argumentos diferentes: una ciudad (representada por `string`) y una fecha (representada por `DateTime`). El almacenamiento interno usa dos clases `Dictionary` para representar el diccionario bidimensional. La API pública ya no representa el almacenamiento subyacente. En su lugar, las características del lenguaje de los indizadores le permiten crear una interfaz pública que representa la abstracción, aunque el almacenamiento subyacente debe usar distintos tipos de colección básica.

Hay dos partes de este código que pueden resultar desconocidas para algunos desarrolladores, Estas dos directivas `using`:

```csharp
using DateMeasurements = System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>;
using CityDataMeasurements = System.Collections.Generic.Dictionary<string, System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>>;
```

Estas instrucciones crean un *alias* para un tipo genérico construido y permiten que el código use después los nombres `DateMeasurements` y `CityDateMeasurements` (más descriptivos) en vez de la construcción genérica de `Dictionary<DateTime, Measurements>` y `Dictionary<string, Dictionary<DateTime, Measurements> >`.
Esta construcción requiere el uso de los nombres completos de tipo en el lado derecho del signo `=`.

La segunda técnica consiste en quitar las partes de tiempo de cualquier objeto `DateTime` usado para indizarse en las colecciones. .NET no incluye un tipo de solo fecha.
Los desarrolladores usan el tipo `DateTime`, aunque emplean la propiedad `Date` para asegurarse de que cualquier objeto `DateTime` de ese día sea igual.

## <a name="summing-up"></a>Resumen

Debe crear indizadores siempre que tenga un elemento de propiedad en la clase, en la que dicha propiedad no representa un valor único, sino una serie de valores donde cada elemento se identifica mediante un conjunto de argumentos. Estos argumentos únicamente pueden identificar el elemento al que se debe hacer referencia en la colección.
Los indizadores amplían el concepto de las [propiedades](properties.md), en las que un miembro se trata como un elemento de datos desde fuera de la clase, pero como un método desde dentro. Los indizadores permiten que los argumentos busquen un solo elemento en una propiedad que representa un conjunto de elementos.
