---
title: "Cómo: Agregar y tomar elementos de forma individual en una clase BlockingCollection"
description: "Cómo: Agregar y tomar elementos de forma individual en una clase BlockingCollection"
keywords: .NET, .NET Core
author: mairaw
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 2b9d39ab-0993-4453-b021-b04870098bf7
translationtype: Human Translation
ms.sourcegitcommit: c15f2da15c6448cf1c36dea2d5fd53e734bb6608
ms.openlocfilehash: 4f73f3bf2000a0ff4cd600d72bb161206a58d23a

---

# <a name="how-to-add-and-take-items-individually-from-a-blockingcollection"></a>Cómo: Agregar y tomar elementos de forma individual en una clase BlockingCollection

Este ejemplo muestra cómo agregar y quitar elementos de [BlockingCollection&lt;T&gt;]( https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent.BlockingCollection-1) con bloqueo y sin bloqueo. Para obtener más información sobre `BlockingCollection<T>`, consulte [Información general sobre BlockingCollection](blockingcollection-overview.md). 

Para obtener un ejemplo de cómo enumerar un elemento `BlockingCollection<T>` hasta que esté vacío y que así no se agreguen más elementos, consulte [Cómo: Utilizar ForEach para quitar elementos de BlockingCollection](how-to-use-foreach-to-remove.md).

## <a name="example"></a>Ejemplo

```csharp
using System;
using System.Collections.Concurrent;
using System.Threading;
using System.Threading.Tasks;

class Program
{
   static void Main()
   {
      // Increase or decrease this value as desired.
      int itemsToAdd = 500;

      // Preserve all the display output for Adds and Takes
      Console.SetBufferSize(80, (itemsToAdd * 2) + 3);

      // A bounded collection. Increase, decrease, or remove the
      // maximum capacity argument to see how it impacts behavior.
      BlockingCollection<int> numbers = new BlockingCollection<int>(50);


      // A simple blocking consumer with no cancellation.
      Task.Run(() =>
      {
          int i = -1;
          while (!numbers.IsCompleted)
          {
              try
              {
                  i = numbers.Take();
              }
              catch (InvalidOperationException)
              {
                  Console.WriteLine("Adding was completed!");
                  break;
              }
              Console.WriteLine("Take:{0} ", i);

              // Simulate a slow consumer. This will cause
              // collection to fill up fast and thus Adds will block.
              Thread.SpinWait(100000);
          }

          Console.WriteLine("\r\nNo more items to take. Press the Enter key to exit.");
      });

      // A simple blocking producer with no cancellation.
      Task.Run(() =>
      {
          for (int i = 0; i < itemsToAdd; i++) {
              numbers.Add(i);
              Console.WriteLine("Add:{0} Count={1}", i, numbers.Count);
          }

          // See documentation for this method.
          numbers.CompleteAdding();
      });

      // Keep the console display open in debug mode.
      Console.ReadLine();
   }
}

```

## <a name="example"></a>Ejemplo

En este segundo ejemplo se muestra cómo agregar y quitar elementos para que las operaciones no se bloqueen. Si no hay ningún elemento o si se ha alcanzado la capacidad máxima de una colección limitada, o si el periodo de tiempo de espera ya ha transcurrido, la operación `TryAdd` o `TryTake` devuelve el resultado “false”. Esto permite al subproceso hacer algún otro trabajo útil durante un rato, para después volver a intentar recuperar un nuevo elemento o intentar agregar el elemento que no se pudo agregar previamente. Asimismo, el programa también muestra cómo implementar la cancelación cuando se tiene acceso al elemento `BlockingCollection<T>`.

```csharp
using System;
using System.Collections.Concurrent;
using System.Threading;
using System.Threading.Tasks;

class ProgramWithCancellation
{

    static int inputs = 2000;

    static void Main()
    {
        // The token source for issuing the cancelation request.
        CancellationTokenSource cts = new CancellationTokenSource();

        // A blocking collection that can hold no more than 100 items at a time.
        BlockingCollection<int> numberCollection = new BlockingCollection<int>(100);

        // Set console buffer to hold our prodigious output.
        Console.SetBufferSize(80, 2000);

        // The simplest UI thread ever invented.
        Task.Run(() =>
        {
            if (Console.ReadKey(true).KeyChar == 'c')
                cts.Cancel();
        });

        // Start one producer and one consumer.
        Task t1 = Task.Run(() => NonBlockingConsumer(numberCollection, cts.Token));
        Task t2 = Task.Run(() => NonBlockingProducer(numberCollection, cts.Token));

        // Wait for the tasks to complete execution
        Task.WaitAll(t1, t2);

        cts.Dispose();
        Console.WriteLine("Press the Enter key to exit.");
        Console.ReadLine();
    }

    static void NonBlockingConsumer(BlockingCollection<int> bc, CancellationToken ct)
    {
        while (!bc.IsCompleted)
        {
            int nextItem = 0;
            try
            {
                if (!bc.TryTake(out nextItem, 0, ct))
                {
                    Console.WriteLine(" Take Blocked");
                }
                else
                {
                    Console.WriteLine(" Take:{0}", nextItem);
                }
            }

            catch (OperationCanceledException)
            {
                Console.WriteLine("Taking canceled.");
                break;
            }

            // Slow down consumer just a little to cause
            // collection to fill up faster, and lead to "AddBlocked"
            Thread.SpinWait(500000);
        }

        Console.WriteLine("\r\nNo more items to take.");
    }

    static void NonBlockingProducer(BlockingCollection<int> bc, CancellationToken ct)
    {
        int itemToAdd = 0;
        bool success = false;

        do
        {
            // Cancellation causes OCE. We know how to handle it.
            try
            {
                // A shorter timeout causes more failures.
                success = bc.TryAdd(itemToAdd, 2, ct);
            }
            catch (OperationCanceledException)
            {
                Console.WriteLine("Add loop canceled.");
                // Let other threads know we're done in case
                // they aren't monitoring the cancellation token.
                bc.CompleteAdding();
                break;
            }

            if (success)
            {
                Console.WriteLine(" Add:{0}", itemToAdd);
                itemToAdd++;
            }
            else
            {
                Console.Write(" AddBlocked:{0} Count = {1}", itemToAdd.ToString(), bc.Count);
                // Don't increment nextItem. Try again on next iteration.

                //Do something else useful instead.
                UpdateProgress(itemToAdd);
            }

        } while (itemToAdd < inputs);

        // No lock required here because only one producer.
        bc.CompleteAdding();
    }

    static void UpdateProgress(int i)
    {
        double percent = ((double)i / inputs) * 100;
        Console.WriteLine("Percent complete: {0}", percent);
    }
}

```

## <a name="see-also"></a>Vea también

[System.Collections.Concurrent]( https://docs.microsoft.com/dotnet/core/api/System.Collections.Concurrent)

[Información general sobre BlockingCollection](blockingcollection-overview.md)



<!--HONumber=Nov16_HO1-->


