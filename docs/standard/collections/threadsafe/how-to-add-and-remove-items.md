---
title: "Cómo: Agregar y quitar elementos de ConcurrentDictionary"
description: "Cómo: Agregar y quitar elementos de ConcurrentDictionary"
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: b7c04a5f-a8e6-42ae-8c84-0e1ae18896eb
translationtype: Human Translation
ms.sourcegitcommit: c15f2da15c6448cf1c36dea2d5fd53e734bb6608
ms.openlocfilehash: 90ad4f1f0266d948937ed462be15a4d4948ce7f8

---

# <a name="how-to-add-and-remove-items-from-a-concurrentdictionary"></a>Cómo: Agregar y quitar elementos de ConcurrentDictionary

Este ejemplo muestra cómo agregar, recuperar, actualizar y quitar elementos de [System.Collections.Concurrent.ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2). Esta clase de colección es una implementación segura para subprocesos. Es recomendable que la use cada vez que varios subprocesos puedan intentar tener acceso a los elementos de forma simultánea.

`ConcurrentDictionary<TKey, TValue>` proporciona varios métodos útiles que requieren que el código compruebe primero si existe una clave antes de intentar agregar o quitar datos. En la tabla siguiente se enumeran estos métodos útiles y se describe cuándo se deben usar.

Método | Cuándo se usa...
------ | -----------
`AddOrUpdate` | Quiere agregar un nuevo valor para una clave especificada y, si la clave ya existe, quiere reemplazar su valor.
`GetOrAdd` | Quiere recuperar el valor existente de una clave especificada y, si la clave no existe, quiere especificar un par de clave/valor.
`TryAdd`, `TryGetValue`, `TryUpdate`, `TryRemove` | Quiere agregar, obtener, actualizar o quitar un par de clave/valor y, si la clave ya existe o se produce un error en el intento por cualquier otra razón, quiere realizar alguna acción alternativa.

## <a name="example"></a>Ejemplo

```csharp
namespace DictionaryHowTo
{
    using System;
    using System.Collections.Concurrent;
    using System.Collections.Generic;
    using System.Linq;
    using System.Text;
    using System.Threading;
    using System.Threading.Tasks;

    // The type of the Value to store in the dictionary:
    class CityInfo : IEqualityComparer<CityInfo>
    {
        public string Name { get; set; }
        public DateTime lastQueryDate { get; set; }
        public decimal Longitude { get; set; }
        public decimal Latitude { get; set; }
        public int[] RecentHighTemperatures { get; set; }

        public CityInfo(string name, decimal longitude, decimal latitude, int[] temps)
        {
            Name = name;
            lastQueryDate = DateTime.Now;
            Longitude = longitude;
            Latitude = latitude;
            RecentHighTemperatures = temps;
        }

        public CityInfo()
        {
        }

        public CityInfo(string key)
        {
            Name = key;
            // MaxValue means "not initialized"
            Longitude = Decimal.MaxValue;
            Latitude = Decimal.MaxValue;
            lastQueryDate = DateTime.Now;
            RecentHighTemperatures = new int[] { 0 };

        }
        public bool Equals(CityInfo x, CityInfo y)
        {
            return x.Name == y.Name && x.Longitude == y.Longitude && x.Latitude == y.Latitude;
        }

        public int GetHashCode(CityInfo obj)
        {
            CityInfo ci = (CityInfo)obj;
            return ci.Name.GetHashCode();
        }
    }

    class Program
    {
        // Create a new concurrent dictionary.
        static ConcurrentDictionary<string, CityInfo> cities = new ConcurrentDictionary<string, CityInfo>();

        static void Main(string[] args)
        {
            CityInfo[] data = 
            {
                new CityInfo(){ Name = "Boston", Latitude = 42.358769M, Longitude = -71.057806M, RecentHighTemperatures = new int[] {56, 51, 52, 58, 65, 56,53}},
                new CityInfo(){ Name = "Miami", Latitude = 25.780833M, Longitude = -80.195556M, RecentHighTemperatures = new int[] {86,87,88,87,85,85,86}},
                new CityInfo(){ Name = "Los Angeles", Latitude = 34.05M, Longitude = -118.25M, RecentHighTemperatures =   new int[] {67,68,69,73,79,78,78}},
                new CityInfo(){ Name = "Seattle", Latitude = 47.609722M, Longitude =  -122.333056M, RecentHighTemperatures =   new int[] {49,50,53,47,52,52,51}},
                new CityInfo(){ Name = "Toronto", Latitude = 43.716589M, Longitude = -79.340686M, RecentHighTemperatures =   new int[] {53,57, 51,52,56,55,50}},
                new CityInfo(){ Name = "Mexico City", Latitude = 19.432736M, Longitude = -99.133253M, RecentHighTemperatures =   new int[] {72,68,73,77,76,74,73}},
                new CityInfo(){ Name = "Rio de Janiero", Latitude = -22.908333M, Longitude = -43.196389M, RecentHighTemperatures =   new int[] {72,68,73,82,84,78,84}},
                new CityInfo(){ Name = "Quito", Latitude = -0.25M, Longitude = -78.583333M, RecentHighTemperatures =   new int[] {71,69,70,66,65,64,61}}
            };

            // Add some key/value pairs from multiple threads.
            Task[] tasks = new Task[2];

            tasks[0] = Task.Run(() =>
            {
                for (int i = 0; i < 2; i++)
                {
                    if (cities.TryAdd(data[i].Name, data[i]))
                        Console.WriteLine("Added {0} on thread {1}", data[i],
                            Thread.CurrentThread.ManagedThreadId);
                    else 
                        Console.WriteLine("Could not add {0}", data[i]);
                }
            });

            tasks[1] = Task.Run(() =>
            {
                for (int i = 2; i < data.Length; i++)
                {
                    if (cities.TryAdd(data[i].Name, data[i]))
                        Console.WriteLine("Added {0} on thread {1}", data[i],
                            Thread.CurrentThread.ManagedThreadId);
                    else
                        Console.WriteLine("Could not add {0}", data[i]);
                }
            });

            // Output results so far.
            Task.WaitAll(tasks);

            // Enumerate collection from the app main thread.
            // Note that ConcurrentDictionary is the one concurrent collection
            // that does not support thread-safe enumeration.
            foreach (var city in cities)
            {
                Console.WriteLine("{0} has been added.", city.Key);
            }

            AddOrUpdateWithoutRetrieving();
            RetrieveValueOrAdd();
            RetrieveAndUpdateOrAdd();  

            Console.WriteLine("Press any key.");
            Console.ReadKey();
        }

        // This method shows how to add key-value pairs to the dictionary
        // in scenarios where the key might already exist.
        private static void AddOrUpdateWithoutRetrieving()
        {
            // Sometime later. We receive new data from some source.
            CityInfo ci = new CityInfo() { Name = "Toronto",
                                            Latitude = 43.716589M,
                                            Longitude = -79.340686M,
                                            RecentHighTemperatures = new int[] { 54, 59, 67, 82, 87, 55, -14 } };

            // Try to add data. If it doesn't exist, the object ci is added. If it does
            // already exist, update existingVal according to the custom logic in the 
            // delegate.
            cities.AddOrUpdate(ci.Name, ci,
                (key, existingVal) =>
                {
                    // If this delegate is invoked, then the key already exists.
                    // Here we make sure the city really is the same city we already have.
                    // (Support for multiple cities of the same name is left as an exercise for the reader.)
                    if (ci != existingVal)
                        throw new ArgumentException("Duplicate city names are not allowed: {0}.", ci.Name);

                    // The only updatable fields are the temerature array and lastQueryDate.
                    existingVal.lastQueryDate = DateTime.Now;
                    existingVal.RecentHighTemperatures = ci.RecentHighTemperatures;
                    return existingVal;
                });

            // Verify that the dictionary contains the new or updated data.
            Console.Write("Most recent high temperatures for {0} are: ", cities[ci.Name].Name);
            int[] temps = cities[ci.Name].RecentHighTemperatures;
            foreach (var temp in temps) Console.Write("{0}, ", temp);
            Console.WriteLine();
        }

        // This method shows how to use data and ensure that it has been
        // added to the dictionary.
        private static void RetrieveValueOrAdd()
        {
            string searchKey = "Caracas";
            CityInfo retrievedValue = null;

            try
            {
                retrievedValue = cities.GetOrAdd(searchKey, GetDataForCity(searchKey));
            }
            catch (ArgumentException e)
            {
                Console.WriteLine(e.Message);
            }

            // Use the data.
            if (retrievedValue != null)
            {
                Console.Write("Most recent high temperatures for {0} are: ", retrievedValue.Name);
                int[] temps = cities[retrievedValue.Name].RecentHighTemperatures;
                foreach (var temp in temps) Console.Write("{0}, ", temp);
            }
            Console.WriteLine();
        }




        // This method shows how to retrieve a value from the dictionary,
        // when you expect that the key/value pair already exists,
        // and then possibly update the dictionary with a new value for the key.
        private static void RetrieveAndUpdateOrAdd()
        {
            CityInfo retrievedValue;
            string searchKey = "Buenos Aires";

            if (cities.TryGetValue(searchKey, out retrievedValue))
            {
                // use the data
                Console.Write("Most recent high temperatures for {0} are: ", retrievedValue.Name);
                int[] temps = retrievedValue.RecentHighTemperatures;
                foreach (var temp in temps) Console.Write("{0}, ", temp);

                // Make a copy of the data. Our object will update its lastQueryDate automatically.
                CityInfo newValue = new CityInfo(retrievedValue.Name,
                                                retrievedValue.Longitude,
                                                retrievedValue.Latitude,
                                                retrievedValue.RecentHighTemperatures);

                // Replace the old value with the new value.
                if (!cities.TryUpdate(searchKey, retrievedValue, newValue))
                {
                    //The data was not updated. Log error, throw exception, etc.
                    Console.WriteLine("Could not update {0}", retrievedValue.Name);
                }
            }
            else
            {
                // Add the new key and value. Here we call a method to retrieve
                // the data. Another option is to add a default value here and 
                // update with real data later on some other thread.
                CityInfo newValue = GetDataForCity(searchKey);
                if( cities.TryAdd(searchKey, newValue))
                {
                    // use the data
                    Console.Write("Most recent high temperatures for {0} are: ", newValue.Name);
                    int[] temps = newValue.RecentHighTemperatures;
                    foreach (var temp in temps) Console.Write("{0}, ", temp);
                }
                else
                    Console.WriteLine("Unable to add data for {0}", searchKey);
            }
        }

        //Assume this method knows how to find long/lat/temp info for any specified city.
        static CityInfo GetDataForCity(string name)
        {
            // Real implementation left as exercise for the reader.
            if (String.CompareOrdinal(name, "Caracas") == 0)
                return new CityInfo() { Name = "Caracas", 
                                        Longitude = 10.5M, 
                                        Latitude = -66.916667M,
                                        RecentHighTemperatures = new int[] { 91, 89, 91, 91, 87, 90, 91 } };
            else if (String.CompareOrdinal(name, "Buenos Aires") == 0)
                return new CityInfo() { Name = "Buenos Aires", 
                                        Longitude = -34.61M, 
                                        Latitude = -58.369997M, 
                                        RecentHighTemperatures = new int[] { 80, 86, 89, 91, 84, 86, 88 } };
            else
                throw new ArgumentException("Cannot find any data for {0}", name);
        }
    }
}

```
[ConcurrentDictionary&lt;TKey, TValue&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentDictionary-2) está diseñado para escenarios multiproceso. No es necesario usar bloqueos en el código para agregar o quitar elementos de la colección. Pero siempre es posible que un subproceso recupere un valor y otro subproceso actualice inmediatamente la colección asignándole un nuevo valor a la misma clave.

Además, aunque todos los métodos de `ConcurrentDictionary<TKey, TValue>` son seguros para subprocesos, no todos los métodos son atómicos, específicamente `GetOrAdd` y `AddOrUpdate`. Se invoca el delegado del usuario que se pasa a estos métodos fuera del bloqueo interno del diccionario. (Esto se hace para evitar que el código desconocido bloquee todos los subprocesos). Por tanto, es posible que se produzca esta secuencia de eventos:

1. el subproceso A llama a `GetOrAdd`, no encuentra ningún elemento y crea un nuevo elemento para agregar invocando al delegado valueFactory.

2. Al mismo tiempo, el subproceso B llama a `GetOrAdd`, se invoca al delegado valueFactory y llega al bloqueo interno antes que el subproceso A y, por tanto, se agrega su nuevo par clave-valor al diccionario.

3. El delegado de usuario del subproceso A se completa, y el subproceso llega al bloqueo, pero ahora se ve que el elemento ya existe.

4. El subproceso A realiza una operación "Get" y devuelve los datos que había agregado anteriormente el subproceso B.

Por tanto, no está garantizado que los datos devueltos por `GetOrAdd` sean los mismos que los creados por valueFactory del subproceso. Puede producirse una secuencia similar de eventos cuando se llama a `AddOrUpdate`. 

## <a name="see-also"></a>Vea también

[System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)

[Colecciones seguras para subprocesos](index.md)




<!--HONumber=Nov16_HO1-->


