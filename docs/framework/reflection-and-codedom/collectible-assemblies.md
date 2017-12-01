---
title: "Ensamblados recopilables para la generación de tipo dinámico"
description: 
ms.date: 08/29/2017
ms.prod: .net
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- reflection, dynamic assembly
- assemblies, collectible
- collectible assemblies, retrieving
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2c9a613f4cc13c3e4189a59ace2e05d01d1bcb4f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="collectible-assemblies-for-dynamic-type-generation"></a>Ensamblados recopilables para la generación de tipo dinámico

*Ensamblados recopilables* son ensamblados dinámicos que se pueden descargar sin descargar el dominio de aplicación en el que se crearon. Se puede reclamar toda la memoria administrada y utilizada por un ensamblado recopilable y los tipos que contiene. Información como el nombre de ensamblado se quita de las tablas internas.

Para habilitar la descarga, use la <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndCollect?displayProperty=nameWithType> marca cuando se crea un ensamblado dinámico. El ensamblado es transitorio (es decir, no se puede guardar) y está sujeto a limitaciones descritas en la [restricciones de los ensamblados recopilables](#restrictions-on-collectible-assemblies) sección. Common language runtime (CLR) descarga automáticamente un ensamblado recopilable cuando libere todos los objetos asociados con el ensamblado. En todos los demás aspectos, los ensamblados recopilables se crean y se usan en la misma manera que otros ensamblados dinámicos.

## <a name="lifetime-of-collectible-assemblies"></a>Duración de los ensamblados recopilables

La duración de un ensamblado recopilable se controla mediante la existencia de referencias a los tipos que contiene y los objetos que se crean a partir de esos tipos. Common language runtime no descarga un ensamblado como uno o varios de los siguientes existen (`T` es cualquier tipo que se define en el ensamblado): 

- Instancia de `T`.

- Una instancia de una matriz de `T`.
 
- Una instancia de un tipo genérico que tiene `T` como uno de sus argumentos de tipo. Esto incluye las colecciones genéricas de `T`, incluso si esa colección está vacía.

- Una instancia de <xref:System.Type> o <xref:System.Reflection.Emit.TypeBuilder> que representa `T`. 

   > [!IMPORTANT]
   > Debe liberar todos los objetos que representan partes del ensamblado. El <xref:System.Reflection.Emit.ModuleBuilder> que define `T` mantiene una referencia a la <xref:System.Reflection.Emit.TypeBuilder>y el <xref:System.Reflection.Emit.AssemblyBuilder> objeto mantiene una referencia a la <xref:System.Reflection.Emit.ModuleBuilder>, por lo que deben liberarse las referencias a estos objetos. Incluso la existencia de un <xref:System.Reflection.Emit.LocalBuilder> o un <xref:System.Reflection.Emit.ILGenerator> utilizados en la fabricación de `T` impide la descarga.

- Una referencia estática a `T` por otro tipo definido dinámicamente `T1` que sigue siendo accesible mediante la ejecución de código. Por ejemplo, `T1` pueden derivar de `T`, o `T` podría ser el tipo de un parámetro en un método de `T1`.
 
- A **ByRef** a un campo estático que pertenece a `T`.

- A <xref:System.RuntimeTypeHandle>, <xref:System.RuntimeFieldHandle>, o <xref:System.RuntimeMethodHandle> que hace referencia a `T` o a un componente de `T`.

- Una instancia de cualquier objeto de reflexión que se podría utilizar de forma indirecta o directamente para tener acceso a la <xref:System.Type> objeto que representa `T`. Por ejemplo, el <xref:System.Type> objeto `T` puede obtenerse a partir de un tipo de matriz cuyo tipo de elemento es `T`, o de un tipo genérico que tiene `T` como un argumento de tipo. 

- Un método `M` en la pila de llamadas de cualquier subproceso, donde `M` es un método de `T` o un método de nivel de módulo que se define en el ensamblado.

- Un delegado a un método estático que se define en un módulo del ensamblado.

Si solo existe un elemento de esta lista para un solo tipo o un método en el ensamblado, el tiempo de ejecución no puede descargar el ensamblado.

> [!NOTE]
> El runtime descarga realmente el ensamblado hasta que se han ejecutado los finalizadores para todos los elementos de la lista.

Para fines de seguimiento de la duración, escriba como un tipo genérico construido `List<int>` (en C#) o `List(Of Integer)` (en Visual Basic) que se crea y utiliza en la generación de un ensamblado recopilable se considera que se han definido en el ensamblado que contiene la interfaz genérica definición de tipo o en un ensamblado que contiene la definición de uno de sus argumentos de tipo. El ensamblado exacto que se usa es un detalle de implementación y sujeto a cambios.
 
## <a name="restrictions-on-collectible-assemblies"></a>Restricciones de los ensamblados recopilables

Las siguientes restricciones se aplican a los ensamblados recopilables: 

- **Referencias estáticas**   
  Tipos en un ensamblado dinámico normal no pueden tener referencias estáticas a tipos que se definen en un ensamblado recopilable. Por ejemplo, si define un tipo normal que hereda de un tipo en un ensamblado recopilable, un <xref:System.NotSupportedException> se produce la excepción. Un tipo en un ensamblado recopilable puede tener referencias estáticas a un tipo en otro ensamblado recopilable, pero esto extiende la duración del ensamblado que se hace referencia a la duración del ensamblado de referencia.

- **Interoperabilidad COM**   
   No hay ninguna interfaz COM se puede definir dentro de un ensamblado recopilable y ninguna instancia de tipos dentro de un ensamblado recopilable se puede convertir en objetos COM. Un tipo en un ensamblado recopilable no puede actuar como un contenedor COM invocable (CCW) o el contenedor invocable en tiempo de ejecución (RCW). Sin embargo, los tipos de ensamblados recopilables pueden usar objetos que implementan interfaces COM.

- **Invocación de plataforma**   
   Métodos que tienen el <xref:System.Runtime.InteropServices.DllImportAttribute> no se compilará el atributo cuando se declaran en un ensamblado recopilable. El <xref:System.Reflection.Emit.OpCodes.Calli?displayProperty=nameWithType> no se puede usar la instrucción en la implementación de un tipo en un ensamblado recopilable y no se puede ordenar estos tipos a código no administrado. Sin embargo, se puede llamar a código nativo mediante el uso de un punto de entrada que se declara en un ensamblado no recopilable.
 
- **El cálculo de referencias**   
   No se pueden calcular las referencias de objetos (en particular, delegados) que se definen en ensamblados recopilables. Se trata de una restricción en todos los tipos transitorios emitidos.

- **Carga de ensamblados**   
   La emisión de reflexión es el único mecanismo que se admite para cargar ensamblados recopilables. Ensamblados que se cargan mediante el uso de cualquier otra forma de carga de ensamblado no se pueden descargar.
 
- **Objetos enlazados a un contexto**    
   No se admiten variables de contexto estático. No se pueden extender tipos en un ensamblado recopilable <xref:System.ContextBoundObject>. Sin embargo, código de ensamblados recopilables puede usar objetos enlazados a un contexto que se definen en otro lugar.

- **Datos estáticos de subproceso**       
   No se admiten variables de subproceso estático.

## <a name="see-also"></a>Vea también

[Emitir métodos y ensamblados dinámicos](emitting-dynamic-methods-and-assemblies.md)
