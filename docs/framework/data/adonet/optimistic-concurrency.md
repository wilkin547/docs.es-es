---
description: 'Más información sobre: simultaneidad optimista'
title: Simultaneidad optimista
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e380edac-da67-4276-80a5-b64decae4947
ms.openlocfilehash: 1034720b2c57b863b87eef440424a7e2f4c2c6c9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739149"
---
# <a name="optimistic-concurrency"></a><span data-ttu-id="e1140-103">Simultaneidad optimista</span><span class="sxs-lookup"><span data-stu-id="e1140-103">Optimistic Concurrency</span></span>

<span data-ttu-id="e1140-104">En un entorno multiusuario existen dos modelos para actualizar datos en una base de datos: simultaneidad optimista y simultaneidad pesimista.</span><span class="sxs-lookup"><span data-stu-id="e1140-104">In a multiuser environment, there are two models for updating data in a database: optimistic concurrency and pessimistic concurrency.</span></span> <span data-ttu-id="e1140-105">El objeto <xref:System.Data.DataSet> está diseñado para fomentar el uso de la simultaneidad optimista en actividades cuya ejecución tiene una larga duración, como cuando se trabaja con interacción remota y cuando los usuarios interactúan con datos.</span><span class="sxs-lookup"><span data-stu-id="e1140-105">The <xref:System.Data.DataSet> object is designed to encourage the use of optimistic concurrency for long-running activities, such as remoting data and interacting with data.</span></span>  
  
 <span data-ttu-id="e1140-106">La simultaneidad pesimista implica bloquear filas en el origen de datos para impedir que otros usuarios modifiquen los datos de tal forma que el usuario actual resulte afectado.</span><span class="sxs-lookup"><span data-stu-id="e1140-106">Pessimistic concurrency involves locking rows at the data source to prevent other users from modifying data in a way that affects the current user.</span></span> <span data-ttu-id="e1140-107">En un modelo pesimista, cuando un usuario realiza una acción que hace que se aplique un bloqueo, otros usuarios no pueden realizar acciones que entrarían en conflicto con el bloqueo hasta que el propietario del bloqueo lo libere.</span><span class="sxs-lookup"><span data-stu-id="e1140-107">In a pessimistic model, when a user performs an action that causes a lock to be applied, other users cannot perform actions that would conflict with the lock until the lock owner releases it.</span></span> <span data-ttu-id="e1140-108">Este modelo se utiliza principalmente en aquellos entornos en los que hay mucha contención de datos, de manera que el costo de proteger los datos con bloqueos es menor que el costo de revertir transacciones si se producen conflictos de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="e1140-108">This model is primarily used in environments where there is heavy contention for data, so that the cost of protecting data with locks is less than the cost of rolling back transactions if concurrency conflicts occur.</span></span>  
  
 <span data-ttu-id="e1140-109">Por tanto, en un modelo de simultaneidad pesimista, un usuario que actualiza una fila establece un bloqueo.</span><span class="sxs-lookup"><span data-stu-id="e1140-109">Therefore, in a pessimistic concurrency model, a user who updates a row establishes a lock.</span></span> <span data-ttu-id="e1140-110">Hasta que el usuario no haya terminado la actualización y liberado el bloqueo, nadie más podrá modificar dicha fila.</span><span class="sxs-lookup"><span data-stu-id="e1140-110">Until the user has finished the update and released the lock, no one else can change that row.</span></span> <span data-ttu-id="e1140-111">Por este motivo, la simultaneidad pesimista resulta más adecuada cuando los tiempos de bloqueo son cortos, como ocurre en el procesamiento de registros mediante programación.</span><span class="sxs-lookup"><span data-stu-id="e1140-111">For this reason, pessimistic concurrency is best implemented when lock times will be short, as in programmatic processing of records.</span></span> <span data-ttu-id="e1140-112">La simultaneidad pesimista no es una opción escalable cuando los usuarios interactúan con los datos y hacen que los registros queden bloqueados durante períodos de tiempo relativamente largos.</span><span class="sxs-lookup"><span data-stu-id="e1140-112">Pessimistic concurrency is not a scalable option when users are interacting with data and causing records to be locked for relatively large periods of time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e1140-113">Si necesita actualizar varias filas en una misma operación, entonces crear una transacción es una opción más escalable que utilizar el bloqueo pesimista.</span><span class="sxs-lookup"><span data-stu-id="e1140-113">If you need to update multiple rows in the same operation, then creating a transaction is a more scalable option than using pessimistic locking.</span></span>  
  
 <span data-ttu-id="e1140-114">Por el contrario, los usuarios que utilizan la simultaneidad optimista no bloquean una fila cuando la leen.</span><span class="sxs-lookup"><span data-stu-id="e1140-114">By contrast, users who use optimistic concurrency do not lock a row when reading it.</span></span> <span data-ttu-id="e1140-115">Cuando un usuario desea actualizar una fila, la aplicación debe determinar si otro usuario la ha modificado o no desde que se leyó.</span><span class="sxs-lookup"><span data-stu-id="e1140-115">When a user wants to update a row, the application must determine whether another user has changed the row since it was read.</span></span> <span data-ttu-id="e1140-116">La simultaneidad optimista suele utilizarse en entornos con poca contención de datos.</span><span class="sxs-lookup"><span data-stu-id="e1140-116">Optimistic concurrency is generally used in environments with a low contention for data.</span></span> <span data-ttu-id="e1140-117">Esto mejora el rendimiento porque no es necesario bloquear registros, a la vez que el bloqueo de registros requiere recursos adicionales del servidor.</span><span class="sxs-lookup"><span data-stu-id="e1140-117">Optimistic concurrency improves performance because no locking of records is required, and locking of records requires additional server resources.</span></span> <span data-ttu-id="e1140-118">Además, para mantener bloqueos de registros es necesaria una conexión persistente con el servidor de bases de datos.</span><span class="sxs-lookup"><span data-stu-id="e1140-118">Also, in order to maintain record locks, a persistent connection to the database server is required.</span></span> <span data-ttu-id="e1140-119">Como éste no es el caso en un modelo de simultaneidad optimista, las conexiones con el servidor pueden atender a un mayor número de clientes en menos tiempo.</span><span class="sxs-lookup"><span data-stu-id="e1140-119">Because this is not the case in an optimistic concurrency model, connections to the server are free to serve a larger number of clients in less time.</span></span>  
  
 <span data-ttu-id="e1140-120">En un modelo de simultaneidad optimista, se considera que ha habido una infracción si, después de que un usuario recibe un valor de la base de datos, otro usuario modifica el valor antes de que el primer usuario haya intentado modificarlo.</span><span class="sxs-lookup"><span data-stu-id="e1140-120">In an optimistic concurrency model, a violation is considered to have occurred if, after a user receives a value from the database, another user modifies the value before the first user has attempted to modify it.</span></span> <span data-ttu-id="e1140-121">En el ejemplo siguiente se describe cómo el servidor resuelve una infracción de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="e1140-121">How the server resolves a concurrency violation is best shown by first describing the following example.</span></span>  
  
 <span data-ttu-id="e1140-122">Las siguientes tablas muestran un ejemplo de simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="e1140-122">The following tables follow an example of optimistic concurrency.</span></span>  
  
 <span data-ttu-id="e1140-123">A la 1:00 p.m., el Usuario1 lee una fila de la base de datos con los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="e1140-123">At 1:00 p.m., User1 reads a row from the database with the following values:</span></span>  
  
 <span data-ttu-id="e1140-124">**IdCliente     Apellido     Nombre**</span><span class="sxs-lookup"><span data-stu-id="e1140-124">**CustID     LastName     FirstName**</span></span>  
  
 <span data-ttu-id="e1140-125">101          Martínez             Cris</span><span class="sxs-lookup"><span data-stu-id="e1140-125">101          Smith             Bob</span></span>  
  
|<span data-ttu-id="e1140-126">Nombre de la columna</span><span class="sxs-lookup"><span data-stu-id="e1140-126">Column name</span></span>|<span data-ttu-id="e1140-127">Valor original</span><span class="sxs-lookup"><span data-stu-id="e1140-127">Original value</span></span>|<span data-ttu-id="e1140-128">Valor actual</span><span class="sxs-lookup"><span data-stu-id="e1140-128">Current value</span></span>|<span data-ttu-id="e1140-129">Valor en la base de datos</span><span class="sxs-lookup"><span data-stu-id="e1140-129">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="e1140-130">IdCliente</span><span class="sxs-lookup"><span data-stu-id="e1140-130">CustID</span></span>|<span data-ttu-id="e1140-131">101</span><span class="sxs-lookup"><span data-stu-id="e1140-131">101</span></span>|<span data-ttu-id="e1140-132">101</span><span class="sxs-lookup"><span data-stu-id="e1140-132">101</span></span>|<span data-ttu-id="e1140-133">101</span><span class="sxs-lookup"><span data-stu-id="e1140-133">101</span></span>|  
|<span data-ttu-id="e1140-134">Apellidos</span><span class="sxs-lookup"><span data-stu-id="e1140-134">LastName</span></span>|<span data-ttu-id="e1140-135">Smith</span><span class="sxs-lookup"><span data-stu-id="e1140-135">Smith</span></span>|<span data-ttu-id="e1140-136">Smith</span><span class="sxs-lookup"><span data-stu-id="e1140-136">Smith</span></span>|<span data-ttu-id="e1140-137">Smith</span><span class="sxs-lookup"><span data-stu-id="e1140-137">Smith</span></span>|  
|<span data-ttu-id="e1140-138">Nombre</span><span class="sxs-lookup"><span data-stu-id="e1140-138">FirstName</span></span>|<span data-ttu-id="e1140-139">Bob</span><span class="sxs-lookup"><span data-stu-id="e1140-139">Bob</span></span>|<span data-ttu-id="e1140-140">Bob</span><span class="sxs-lookup"><span data-stu-id="e1140-140">Bob</span></span>|<span data-ttu-id="e1140-141">Bob</span><span class="sxs-lookup"><span data-stu-id="e1140-141">Bob</span></span>|  
  
 <span data-ttu-id="e1140-142">A la 1:01 p.m., el Usuario2 lee la misma fila.</span><span class="sxs-lookup"><span data-stu-id="e1140-142">At 1:01 p.m., User2 reads the same row.</span></span>  
  
 <span data-ttu-id="e1140-143">A las 13:03, el Usuario2 cambia **FirstName** de "Cris" a "Cristina" y actualiza la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e1140-143">At 1:03 p.m., User2 changes **FirstName** from "Bob" to "Robert" and updates the database.</span></span>  
  
|<span data-ttu-id="e1140-144">Nombre de la columna</span><span class="sxs-lookup"><span data-stu-id="e1140-144">Column name</span></span>|<span data-ttu-id="e1140-145">Valor original</span><span class="sxs-lookup"><span data-stu-id="e1140-145">Original value</span></span>|<span data-ttu-id="e1140-146">Valor actual</span><span class="sxs-lookup"><span data-stu-id="e1140-146">Current value</span></span>|<span data-ttu-id="e1140-147">Valor en la base de datos</span><span class="sxs-lookup"><span data-stu-id="e1140-147">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="e1140-148">IdCliente</span><span class="sxs-lookup"><span data-stu-id="e1140-148">CustID</span></span>|<span data-ttu-id="e1140-149">101</span><span class="sxs-lookup"><span data-stu-id="e1140-149">101</span></span>|<span data-ttu-id="e1140-150">101</span><span class="sxs-lookup"><span data-stu-id="e1140-150">101</span></span>|<span data-ttu-id="e1140-151">101</span><span class="sxs-lookup"><span data-stu-id="e1140-151">101</span></span>|  
|<span data-ttu-id="e1140-152">Apellidos</span><span class="sxs-lookup"><span data-stu-id="e1140-152">LastName</span></span>|<span data-ttu-id="e1140-153">Smith</span><span class="sxs-lookup"><span data-stu-id="e1140-153">Smith</span></span>|<span data-ttu-id="e1140-154">Smith</span><span class="sxs-lookup"><span data-stu-id="e1140-154">Smith</span></span>|<span data-ttu-id="e1140-155">Smith</span><span class="sxs-lookup"><span data-stu-id="e1140-155">Smith</span></span>|  
|<span data-ttu-id="e1140-156">Nombre</span><span class="sxs-lookup"><span data-stu-id="e1140-156">FirstName</span></span>|<span data-ttu-id="e1140-157">Bob</span><span class="sxs-lookup"><span data-stu-id="e1140-157">Bob</span></span>|<span data-ttu-id="e1140-158">Cristina</span><span class="sxs-lookup"><span data-stu-id="e1140-158">Robert</span></span>|<span data-ttu-id="e1140-159">Bob</span><span class="sxs-lookup"><span data-stu-id="e1140-159">Bob</span></span>|  
  
 <span data-ttu-id="e1140-160">La actualización se realiza correctamente porque los valores contenidos en la base de datos en el momento de la actualización coinciden con los valores originales que tiene el Usuario2.</span><span class="sxs-lookup"><span data-stu-id="e1140-160">The update succeeds because the values in the database at the time of update match the original values that User2 has.</span></span>  
  
 <span data-ttu-id="e1140-161">A la 1:05 p.m., el Usuario1 cambia el nombre de "Cris" a "Jaime" e intenta actualizar la fila.</span><span class="sxs-lookup"><span data-stu-id="e1140-161">At 1:05 p.m., User1 changes "Bob"'s first name to "James" and tries to update the row.</span></span>  
  
|<span data-ttu-id="e1140-162">Nombre de la columna</span><span class="sxs-lookup"><span data-stu-id="e1140-162">Column name</span></span>|<span data-ttu-id="e1140-163">Valor original</span><span class="sxs-lookup"><span data-stu-id="e1140-163">Original value</span></span>|<span data-ttu-id="e1140-164">Valor actual</span><span class="sxs-lookup"><span data-stu-id="e1140-164">Current value</span></span>|<span data-ttu-id="e1140-165">Valor en la base de datos</span><span class="sxs-lookup"><span data-stu-id="e1140-165">Value in database</span></span>|  
|-----------------|--------------------|-------------------|-----------------------|  
|<span data-ttu-id="e1140-166">IdCliente</span><span class="sxs-lookup"><span data-stu-id="e1140-166">CustID</span></span>|<span data-ttu-id="e1140-167">101</span><span class="sxs-lookup"><span data-stu-id="e1140-167">101</span></span>|<span data-ttu-id="e1140-168">101</span><span class="sxs-lookup"><span data-stu-id="e1140-168">101</span></span>|<span data-ttu-id="e1140-169">101</span><span class="sxs-lookup"><span data-stu-id="e1140-169">101</span></span>|  
|<span data-ttu-id="e1140-170">Apellidos</span><span class="sxs-lookup"><span data-stu-id="e1140-170">LastName</span></span>|<span data-ttu-id="e1140-171">Smith</span><span class="sxs-lookup"><span data-stu-id="e1140-171">Smith</span></span>|<span data-ttu-id="e1140-172">Smith</span><span class="sxs-lookup"><span data-stu-id="e1140-172">Smith</span></span>|<span data-ttu-id="e1140-173">Smith</span><span class="sxs-lookup"><span data-stu-id="e1140-173">Smith</span></span>|  
|<span data-ttu-id="e1140-174">Nombre</span><span class="sxs-lookup"><span data-stu-id="e1140-174">FirstName</span></span>|<span data-ttu-id="e1140-175">Bob</span><span class="sxs-lookup"><span data-stu-id="e1140-175">Bob</span></span>|<span data-ttu-id="e1140-176">Jaime</span><span class="sxs-lookup"><span data-stu-id="e1140-176">James</span></span>|<span data-ttu-id="e1140-177">Cristina</span><span class="sxs-lookup"><span data-stu-id="e1140-177">Robert</span></span>|  
  
 <span data-ttu-id="e1140-178">En este momento, el Usuario1 encuentra una infracción de la simultaneidad optimista porque los valores de la base de datos ("Jaime") ya no coinciden con los valores originales que esperaba el Usuario1 ("Cris").</span><span class="sxs-lookup"><span data-stu-id="e1140-178">At this point, User1 encounters an optimistic concurrency violation because the value in the database ("Robert") no longer matches the original value that User1 was expecting ("Bob").</span></span> <span data-ttu-id="e1140-179">La infracción de simultaneidad simplemente permite saber que se ha producido un error de actualización.</span><span class="sxs-lookup"><span data-stu-id="e1140-179">The concurrency violation simply lets you know that the update failed.</span></span> <span data-ttu-id="e1140-180">Ahora hay que tomar la decisión de sobrescribir los cambios realizados por el Usuario2 con los efectuados por el Usuario1 o cancelar los cambios del Usuario1.</span><span class="sxs-lookup"><span data-stu-id="e1140-180">The decision now needs to be made whether to overwrite the changes supplied by User2 with the changes supplied by User1, or to cancel the changes by User1.</span></span>  
  
## <a name="testing-for-optimistic-concurrency-violations"></a><span data-ttu-id="e1140-181">Probar si hay infracciones de la simultaneidad optimista</span><span class="sxs-lookup"><span data-stu-id="e1140-181">Testing for Optimistic Concurrency Violations</span></span>  

 <span data-ttu-id="e1140-182">Existen varias técnicas para probar si se ha producido una infracción de la simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="e1140-182">There are several techniques for testing for an optimistic concurrency violation.</span></span> <span data-ttu-id="e1140-183">Una de ellas consiste en incluir una columna de marca de tiempo en la tabla.</span><span class="sxs-lookup"><span data-stu-id="e1140-183">One involves including a timestamp column in the table.</span></span> <span data-ttu-id="e1140-184">Las bases de datos suelen ofrecer funcionalidad de marca de tiempo que puede utilizarse para identificar la fecha y la hora en que se actualizó el registro por última vez.</span><span class="sxs-lookup"><span data-stu-id="e1140-184">Databases commonly provide timestamp functionality that can be used to identify the date and time when the record was last updated.</span></span> <span data-ttu-id="e1140-185">Mediante esta técnica se incluye una columna de marca de tiempo en la definición de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e1140-185">Using this technique, a timestamp column is included in the table definition.</span></span> <span data-ttu-id="e1140-186">Siempre que se actualiza el registro, se actualiza la marca de tiempo de manera que queden reflejadas la fecha y la hora actuales.</span><span class="sxs-lookup"><span data-stu-id="e1140-186">Whenever the record is updated, the timestamp is updated to reflect the current date and time.</span></span> <span data-ttu-id="e1140-187">Al hacer una prueba para ver si hay infracciones de la simultaneidad optimista, la columna de marca de tiempo se devuelve con cualquier consulta del contenido de la tabla.</span><span class="sxs-lookup"><span data-stu-id="e1140-187">In a test for optimistic concurrency violations, the timestamp column is returned with any query of the contents of the table.</span></span> <span data-ttu-id="e1140-188">Cuando se intenta realizar una actualización, se compara el valor de marca de tiempo de la base de datos con el valor de marca de tiempo original contenido en la fila modificada.</span><span class="sxs-lookup"><span data-stu-id="e1140-188">When an update is attempted, the timestamp value in the database is compared to the original timestamp value contained in the modified row.</span></span> <span data-ttu-id="e1140-189">Si coinciden, se realiza la actualización y se actualiza la columna de marca de tiempo con la hora actual con el fin de reflejar la actualización.</span><span class="sxs-lookup"><span data-stu-id="e1140-189">If they match, the update is performed and the timestamp column is updated with the current time to reflect the update.</span></span> <span data-ttu-id="e1140-190">Si no coinciden, se ha producido una infracción de la simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="e1140-190">If they do not match, an optimistic concurrency violation has occurred.</span></span>  
  
 <span data-ttu-id="e1140-191">Otra técnica para probar si hay alguna infracción relacionada con la simultaneidad optimista consiste en comprobar que todos los valores de columna originales de una fila siguen coincidiendo con los existentes en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e1140-191">Another technique for testing for an optimistic concurrency violation is to verify that all the original column values in a row still match those found in the database.</span></span> <span data-ttu-id="e1140-192">Por ejemplo, considere la siguiente consulta:</span><span class="sxs-lookup"><span data-stu-id="e1140-192">For example, consider the following query:</span></span>  
  
```sql
SELECT Col1, Col2, Col3 FROM Table1  
```  
  
 <span data-ttu-id="e1140-193">Para probar si hay alguna infracción de simultaneidad optimista al actualizar una fila de **Table1**, tendría que emitir la siguiente instrucción UPDATE:</span><span class="sxs-lookup"><span data-stu-id="e1140-193">To test for an optimistic concurrency violation when updating a row in **Table1**, you would issue the following UPDATE statement:</span></span>  
  
```sql
UPDATE Table1 Set Col1 = @NewCol1Value,  
              Set Col2 = @NewCol2Value,  
              Set Col3 = @NewCol3Value  
WHERE Col1 = @OldCol1Value AND  
      Col2 = @OldCol2Value AND  
      Col3 = @OldCol3Value  
```  
  
 <span data-ttu-id="e1140-194">La actualización se realizará siempre y cuando los valores originales coincidan con los valores de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="e1140-194">As long as the original values match the values in the database, the update is performed.</span></span> <span data-ttu-id="e1140-195">Si se ha modificado algún valor, la actualización no modificará la fila porque la cláusula WHERE no encontrará ninguna coincidencia.</span><span class="sxs-lookup"><span data-stu-id="e1140-195">If a value has been modified, the update will not modify the row because the WHERE clause will not find a match.</span></span>  
  
 <span data-ttu-id="e1140-196">Se recomienda devolver siempre un valor de clave principal único en la consulta.</span><span class="sxs-lookup"><span data-stu-id="e1140-196">Note that it is recommended to always return a unique primary key value in your query.</span></span> <span data-ttu-id="e1140-197">De lo contrario, la instrucción UPDATE anterior puede actualizar más de una fila, lo que quizás no sea su intención.</span><span class="sxs-lookup"><span data-stu-id="e1140-197">Otherwise, the preceding UPDATE statement may update more than one row, which might not be your intent.</span></span>  
  
 <span data-ttu-id="e1140-198">Si una columna del origen de datos admite valores nulos, quizás sea necesario extender la cláusula WHERE para comprobar si hay alguna referencia nula coincidente en la tabla local y en el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e1140-198">If a column at your data source allows nulls, you may need to extend your WHERE clause to check for a matching null reference in your local table and at the data source.</span></span> <span data-ttu-id="e1140-199">Por ejemplo, la siguiente instrucción UPDATE comprueba que una referencia nula de la fila local sigue coincidiendo con una referencia nula del origen de datos o que el valor de la fila local sigue coincidiendo con el valor del origen de datos.</span><span class="sxs-lookup"><span data-stu-id="e1140-199">For example, the following UPDATE statement verifies that a null reference in the local row still matches a null reference at the data source, or that the value in the local row still matches the value at the data source.</span></span>  
  
```sql
UPDATE Table1 Set Col1 = @NewVal1  
  WHERE (@OldVal1 IS NULL AND Col1 IS NULL) OR Col1 = @OldVal1  
```  
  
 <span data-ttu-id="e1140-200">También se puede decidir la aplicación de criterios menos restrictivos al utilizar un modelo de simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="e1140-200">You may also choose to apply less restrictive criteria when using an optimistic concurrency model.</span></span> <span data-ttu-id="e1140-201">Por ejemplo, si solo se utilizan las columnas de clave principal en la cláusula WHERE se sobrescribirán los datos, independientemente de que las otras columnas se hayan actualizado o no desde la última consulta.</span><span class="sxs-lookup"><span data-stu-id="e1140-201">For example, using only the primary key columns in the WHERE clause causes the data to be overwritten regardless of whether the other columns have been updated since the last query.</span></span> <span data-ttu-id="e1140-202">También se puede aplicar una cláusula WHERE solo a determinadas columnas, lo que hará que se sobrescriban los datos a menos que se hayan actualizado ciertos campos desde que se consultaron por última vez.</span><span class="sxs-lookup"><span data-stu-id="e1140-202">You can also apply a WHERE clause only to specific columns, resulting in data being overwritten unless particular fields have been updated since they were last queried.</span></span>  
  
### <a name="the-dataadapterrowupdated-event"></a><span data-ttu-id="e1140-203">Evento DataAdapter.RowUpdated</span><span class="sxs-lookup"><span data-stu-id="e1140-203">The DataAdapter.RowUpdated Event</span></span>  

 <span data-ttu-id="e1140-204">El evento **RowUpdated** del objeto <xref:System.Data.Common.DataAdapter> se puede usar junto con las técnicas descritas anteriormente para notificar a la aplicación las infracciones de simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="e1140-204">The **RowUpdated** event of the <xref:System.Data.Common.DataAdapter> object can be used in conjunction with the techniques described earlier, to provide notification to your application of optimistic concurrency violations.</span></span> <span data-ttu-id="e1140-205">**RowUpdated** se produce después de cada intento de actualizar una fila **Modified** de un objeto **DataSet**.</span><span class="sxs-lookup"><span data-stu-id="e1140-205">**RowUpdated** occurs after each attempt to update a **Modified** row from a **DataSet**.</span></span> <span data-ttu-id="e1140-206">Esto permite agregar código especial de control, incluyendo el procesamiento cuando se produce una excepción, agregar información de error personalizada, agregar lógica de reintento, etc.</span><span class="sxs-lookup"><span data-stu-id="e1140-206">This enables you to add special handling code, including processing when an exception occurs, adding custom error information, adding retry logic, and so on.</span></span> <span data-ttu-id="e1140-207">El objeto <xref:System.Data.Common.RowUpdatedEventArgs> devuelve una propiedad **RecordsAffected** con el número de filas afectadas por un determinado comando de actualización para una fila modificada de una tabla.</span><span class="sxs-lookup"><span data-stu-id="e1140-207">The <xref:System.Data.Common.RowUpdatedEventArgs> object returns a **RecordsAffected** property containing the number of rows affected by a particular update command for a modified row in a table.</span></span> <span data-ttu-id="e1140-208">Al establecer el comando de actualización para que compruebe la simultaneidad optimista, la propiedad **RecordsAffected** devolverá un valor 0 cuando se haya producido una infracción en la simultaneidad optimista, ya que no se ha actualizado ningún registro.</span><span class="sxs-lookup"><span data-stu-id="e1140-208">By setting the update command to test for optimistic concurrency, the **RecordsAffected** property will, as a result, return a value of 0 when an optimistic concurrency violation has occurred, because no records were updated.</span></span> <span data-ttu-id="e1140-209">En tal caso se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="e1140-209">If this is the case, an exception is thrown.</span></span> <span data-ttu-id="e1140-210">El evento **RowUpdated** le permite controlar este caso y evitar la excepción al establecer un valor **RowUpdatedEventArgs.Status** apropiado, como **UpdateStatus.SkipCurrentRow**.</span><span class="sxs-lookup"><span data-stu-id="e1140-210">The **RowUpdated** event enables you to handle this occurrence and avoid the exception by setting an appropriate **RowUpdatedEventArgs.Status** value, such as **UpdateStatus.SkipCurrentRow**.</span></span> <span data-ttu-id="e1140-211">Para obtener más información sobre el evento **RowUpdated**, vea [Control de eventos de objetos DataAdapter](handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="e1140-211">For more information about the **RowUpdated** event, see [Handling DataAdapter Events](handling-dataadapter-events.md).</span></span>  
  
 <span data-ttu-id="e1140-212">De forma opcional, puede establecer **DataAdapter.ContinueUpdateOnError** en **true** antes de llamar a **Update** y responder a la información de error almacenada en la propiedad **RowError** de una fila determinada cuando **Update** se complete.</span><span class="sxs-lookup"><span data-stu-id="e1140-212">Optionally, you can set **DataAdapter.ContinueUpdateOnError** to **true**, before calling **Update**, and respond to the error information stored in the **RowError** property of a particular row when the **Update** is completed.</span></span> <span data-ttu-id="e1140-213">Para obtener más información, vea [Información de error de fila](./dataset-datatable-dataview/row-error-information.md).</span><span class="sxs-lookup"><span data-stu-id="e1140-213">For more information, see [Row Error Information](./dataset-datatable-dataview/row-error-information.md).</span></span>  
  
## <a name="optimistic-concurrency-example"></a><span data-ttu-id="e1140-214">Ejemplo de simultaneidad optimista</span><span class="sxs-lookup"><span data-stu-id="e1140-214">Optimistic Concurrency Example</span></span>  

 <span data-ttu-id="e1140-215">A continuación se muestra un ejemplo sencillo que establece **UpdateCommand** de **DataAdapter** para probar la simultaneidad optimista y, después, usa el evento **RowUpdated** para probar si hay infracciones de la simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="e1140-215">The following is a simple example that sets the **UpdateCommand** of a **DataAdapter** to test for optimistic concurrency, and then uses the **RowUpdated** event to test for optimistic concurrency violations.</span></span> <span data-ttu-id="e1140-216">Cuando se encuentra una infracción de simultaneidad optimista, la aplicación establece el valor **RowError** de la fila para la que se ha emitido la actualización con el fin de reflejar la existencia de una infracción de la simultaneidad optimista.</span><span class="sxs-lookup"><span data-stu-id="e1140-216">When an optimistic concurrency violation is encountered, the application sets the **RowError** of the row that the update was issued for to reflect an optimistic concurrency violation.</span></span>  
  
 <span data-ttu-id="e1140-217">Tenga en cuenta que los valores de los parámetros pasados a la cláusula WHERE del comando UPDATE se asignan a los valores **Original** de sus respectivas columnas.</span><span class="sxs-lookup"><span data-stu-id="e1140-217">Note that the parameter values passed to the WHERE clause of the UPDATE command are mapped to the **Original** values of their respective columns.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID", _  
  connection)  
  
' The Update command checks for optimistic concurrency violations  
' in the WHERE clause.  
adapter.UpdateCommand = New SqlCommand("UPDATE Customers " &  
  "(CustomerID, CompanyName) VALUES(@CustomerID, @CompanyName) " & _  
  "WHERE CustomerID = @oldCustomerID AND CompanyName = " &  
  "@oldCompanyName", connection)  
adapter.UpdateCommand.Parameters.Add( _  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
adapter.UpdateCommand.Parameters.Add( _  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
  
' Pass the original values to the WHERE clause parameters.  
Dim parameter As SqlParameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
parameter.SourceVersion = DataRowVersion.Original  
parameter = adapter.UpdateCommand.Parameters.Add( _  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName")  
parameter.SourceVersion = DataRowVersion.Original  
  
' Add the RowUpdated event handler.  
AddHandler adapter.RowUpdated, New SqlRowUpdatedEventHandler( _  
  AddressOf OnRowUpdated)  
  
Dim dataSet As DataSet = New DataSet()  
adapter.Fill(dataSet, "Customers")  
  
' Modify the DataSet contents.  
adapter.Update(dataSet, "Customers")  
  
Dim dataRow As DataRow  
  
For Each dataRow In dataSet.Tables("Customers").Rows  
    If dataRow.HasErrors Then
       Console.WriteLine(dataRow (0) & vbCrLf & dataRow.RowError)  
    End If  
Next  
  
Private Shared Sub OnRowUpdated( _  
  sender As object, args As SqlRowUpdatedEventArgs)  
   If args.RecordsAffected = 0  
      args.Row.RowError = "Optimistic Concurrency Violation!"  
      args.Status = UpdateStatus.SkipCurrentRow  
   End If  
End Sub  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT CustomerID, CompanyName FROM Customers ORDER BY CustomerID",  
  connection);  
  
// The Update command checks for optimistic concurrency violations  
// in the WHERE clause.  
adapter.UpdateCommand = new SqlCommand("UPDATE Customers Set CustomerID = @CustomerID, CompanyName = @CompanyName " +  
   "WHERE CustomerID = @oldCustomerID AND CompanyName = @oldCompanyName", connection);  
adapter.UpdateCommand.Parameters.Add(  
  "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
adapter.UpdateCommand.Parameters.Add(  
  "@CompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
  
// Pass the original values to the WHERE clause parameters.  
SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
parameter.SourceVersion = DataRowVersion.Original;  
parameter = adapter.UpdateCommand.Parameters.Add(  
  "@oldCompanyName", SqlDbType.NVarChar, 30, "CompanyName");  
parameter.SourceVersion = DataRowVersion.Original;  
  
// Add the RowUpdated event handler.  
adapter.RowUpdated += new SqlRowUpdatedEventHandler(OnRowUpdated);  
  
DataSet dataSet = new DataSet();  
adapter.Fill(dataSet, "Customers");  
  
// Modify the DataSet contents.  
  
adapter.Update(dataSet, "Customers");  
  
foreach (DataRow dataRow in dataSet.Tables["Customers"].Rows)  
{  
    if (dataRow.HasErrors)  
       Console.WriteLine(dataRow [0] + "\n" + dataRow.RowError);  
}  
  
protected static void OnRowUpdated(object sender, SqlRowUpdatedEventArgs args)  
{  
  if (args.RecordsAffected == 0)
  {  
    args.Row.RowError = "Optimistic Concurrency Violation Encountered";  
    args.Status = UpdateStatus.SkipCurrentRow;  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e1140-218">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1140-218">See also</span></span>

- [<span data-ttu-id="e1140-219">Recuperar y modificar datos en ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e1140-219">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="e1140-220">Actualizar orígenes de datos con objetos DataAdapter</span><span class="sxs-lookup"><span data-stu-id="e1140-220">Updating Data Sources with DataAdapters</span></span>](updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="e1140-221">Información de error de fila</span><span class="sxs-lookup"><span data-stu-id="e1140-221">Row Error Information</span></span>](./dataset-datatable-dataview/row-error-information.md)
- [<span data-ttu-id="e1140-222">Transacciones y simultaneidad</span><span class="sxs-lookup"><span data-stu-id="e1140-222">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="e1140-223">Información general de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e1140-223">ADO.NET Overview</span></span>](ado-net-overview.md)
