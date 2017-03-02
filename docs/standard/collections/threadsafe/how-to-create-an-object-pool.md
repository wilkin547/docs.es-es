---
title: "Cómo: Crear un grupo de objetos usando ConcurrentBag"
description: "Cómo: Crear un grupo de objetos usando ConcurrentBag"
keywords: .NET, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 87a6ada1-ee27-423d-b587-82e7cb45361b
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: c2a37ff23c65cb2c4743935c6939816a0cea7e86
ms.lasthandoff: 03/02/2017

---

# <a name="how-to-create-an-object-pool-by-using-a-concurrentbag"></a>Cómo: Crear un grupo de objetos usando ConcurrentBag

Este ejemplo muestra cómo usar un contenedor simultáneo para implementar un grupo de objetos. Los grupos de objetos pueden mejorar el rendimiento de la aplicación en situaciones donde se requieren varias instancias de una clase y cuesta mucho crear o destruir la clase. Cuando un programa cliente solicita un nuevo objeto, el grupo de objetos primero intenta proporcionar uno que ya se ha creado y devuelto al grupo. Si no hay ninguno disponible, solo entonces se crea un nuevo objeto. 

[ConcurrentBag&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentBag-1) se usa para almacenar los objetos porque admite la inserción y eliminación rápidas, especialmente cuando el mismo subproceso agrega y quita elementos. Este ejemplo se podría ampliar aún más para crearse en torno a [IProducerConsumerCollection&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.IProducerConsumerCollection-1), que implementa la estructura de datos del contenedor, al igual que [ConcurrentQueue&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentQueue-1) y [ConcurrentStack&lt;T&gt;](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.ConcurrentStack-1).

## <a name="example"></a>Ejemplo

```csharp
using System;
using System.Collections.Concurrent;
using System.Threading;
using System.Threading.Tasks;


namespace ObjectPoolExample
{
    public class ObjectPool<T>
    {
        private ConcurrentBag<T> _objects;
        private Func<T> _objectGenerator;

        public ObjectPool(Func<T> objectGenerator)
        {
            if (objectGenerator == null) throw new ArgumentNullException("objectGenerator");

            _objects = new ConcurrentBag<T>();
            _objectGenerator = objectGenerator;
        }

        public T GetObject()
        {
            T item;
            return _objects.TryTake(out item) ? item : _objectGenerator();
        }

        public void PutObject(T item)
        {
            _objects.Add(item);
        }
    }

    class Program
    {
       static void Main(string[] args)
        {
            CancellationTokenSource cts = new CancellationTokenSource();

            // Create an opportunity for the user to cancel.
            Task.Run(() =>
                {
                    if (Console.ReadKey().KeyChar == 'c' || Console.ReadKey().KeyChar == 'C')
                        cts.Cancel();
                });

            ObjectPool<MyClass> pool = new ObjectPool<MyClass> (() => new MyClass());            

            // Create a high demand for MyClass objects.
            Parallel.For(0, 1000000, (i, loopState) =>
                {
                    MyClass mc = pool.GetObject();
                    Console.CursorLeft = 0;
                    // This is the bottleneck in our application. All threads in this loop
                    // must serialize their access to the static Console class.
                    Console.WriteLine("{0:####.####}", mc.GetValue(i));                 

                    pool.PutObject(mc);
                    if (cts.Token.IsCancellationRequested)
                        loopState.Stop();                 
                });
            Console.WriteLine("Press the Enter key to exit.");
            Console.ReadLine();
            cts.Dispose();
        }
    }

    // A toy class that requires some resources to create.
    // You can experiment here to measure the performance of the
    // object pool vs. ordinary instantiation.
    class MyClass
    {
        public int[] Nums {get; set;}
        public double GetValue(long i)
        {
            return Math.Sqrt(Nums[i]);
        }
        public MyClass()
        {
            Nums = new int[1000000];
            Random rand = new Random();
            for (int i = 0; i < Nums.Length; i++)
                Nums[i] = rand.Next();
        }
    }   
}
```

## <a name="see-also"></a>Vea también

[System.Collections.Concurrent](https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)

[Colecciones seguras para subprocesos](index.md)



