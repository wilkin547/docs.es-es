---
title: Ensamblados recopilables para la generación dinámica de tipos
description: Empiece a usar ensamblados recopilables para la generación dinámica de tipos en .NET. Lea sobre la duración y las restricciones de los ensamblados recopilables.
ms.date: 08/29/2017
helpviewer_keywords:
- reflection, dynamic assembly
- assemblies, collectible
- collectible assemblies, retrieving
ms.openlocfilehash: 4981b93dbd49a6da96740bebed0f2ed7b89036c8
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475130"
---
# <a name="collectible-assemblies-for-dynamic-type-generation"></a>Ensamblados recopilables para la generación dinámica de tipos

Los *ensamblados recopilables* son ensamblados dinámicos que se pueden descargar sin descargar el dominio de aplicación en el que se crearon. Se puede reclamar toda la memoria administrada y sin administrar usada por un ensamblado recopilable y los tipos que contiene. La información como el nombre de ensamblado se quita de las tablas internas.

Para habilitar la descarga, use la marca <xref:System.Reflection.Emit.AssemblyBuilderAccess.RunAndCollect?displayProperty=nameWithType> cuando cree un ensamblado dinámico. El ensamblado es transitorio (es decir, no se puede guardar) y está sujeto a las limitaciones descritas en la sección [Restricciones de los ensamblados recopilables](#restrictions-on-collectible-assemblies). Common Language Runtime (CLR) descarga automáticamente un ensamblado recopilable cuando se liberan todos los objetos asociados al ensamblado. En todos los demás aspectos, los ensamblados recopilables se crean y se usan de la misma manera que los demás ensamblados dinámicos.

## <a name="lifetime-of-collectible-assemblies"></a>Duración de los ensamblados recopilables

La duración de un ensamblado recopilable se controla mediante referencias a los tipos que contiene y los objetos que se crean a partir de esos tipos. Common Language Runtime no descarga un ensamblado siempre que existan uno o varios de los siguientes (`T` es cualquier tipo definido en el ensamblado):

- Instancia de `T`.

- Una instancia de una matriz de `T`.

- Una instancia de un tipo genérico que tenga `T` como uno de sus argumentos de tipo. Esto incluye las recopilaciones genéricas de `T`, aun cuando esa recopilación esté vacía.

- Una instancia de <xref:System.Type> o <xref:System.Reflection.Emit.TypeBuilder> que represente a `T`.

   > [!IMPORTANT]
   > Debe liberar todos los objetos que representen a partes del ensamblado. El elemento <xref:System.Reflection.Emit.ModuleBuilder> que define `T` mantiene una referencia a <xref:System.Reflection.Emit.TypeBuilder> y el objeto <xref:System.Reflection.Emit.AssemblyBuilder> mantiene una referencia a <xref:System.Reflection.Emit.ModuleBuilder>, así que las referencias a estos objetos deben liberarse. Incluso la existencia de un elemento <xref:System.Reflection.Emit.LocalBuilder> o <xref:System.Reflection.Emit.ILGenerator> usado en la construcción de `T` evita la descarga.

- Una referencia estática a `T` por parte de otro tipo `T1` definido de forma dinámica que siga siendo accesible mediante la ejecución de código. Por ejemplo, `T1` puede derivar de `T`, o `T` puede ser el tipo de un parámetro en un método de `T1`.

- **ByRef** a un campo estático que pertenece a `T`.

- <xref:System.RuntimeTypeHandle>, <xref:System.RuntimeFieldHandle> o <xref:System.RuntimeMethodHandle> que hace referencia a `T` o a un componente de `T`.

- Una instancia de cualquier objeto de reflexión que se pudiera usar de forma directa o indirecta para acceder al objeto <xref:System.Type> que representa `T`. Por ejemplo, el objeto <xref:System.Type> para `T` puede obtenerse a partir de un tipo de matriz cuyo tipo de elemento es `T` o de un tipo genérico que tiene `T` como argumento de tipo.

- Un método `M` en la pila de llamadas de cualquier subproceso, donde `M` es un método de `T` o un método de nivel de módulo definido en el ensamblado.

- Un delegado a un método estático definido en un módulo del ensamblado.

Si solo existe un elemento de esta lista para un solo tipo o un método del ensamblado, el runtime no puede descargar el ensamblado.

> [!NOTE]
> El runtime no descarga realmente el ensamblado hasta que se han ejecutado los finalizadores de todos los elementos de la lista.

Para realizar el seguimiento de la duración, se considera que en el ensamblado que contiene la definición del tipo genérico o en un ensamblado que contiene la definición de uno de sus argumentos de tipo se ha definido un tipo genérico construido `List<int>` (en C#) o `List(Of Integer)` (en Visual Basic) creado y usado en la generación de un ensamblado recopilable. El ensamblado exacto que se usa es un detalle de implementación y está sujeto a cambios.

## <a name="restrictions-on-collectible-assemblies"></a>Restricciones de los ensamblados recopilables

Las siguientes restricciones se aplican a los ensamblados recopilables:

- **Referencias estáticas** Los tipos de un ensamblado dinámico normal no pueden tener referencias estáticas a los tipos definidos en un ensamblado recopilable. Por ejemplo, si define un tipo normal que hereda de un tipo de un ensamblado recopilable, se produce una excepción <xref:System.NotSupportedException>. Un tipo de un ensamblado recopilable puede tener referencias estáticas a un tipo de otro ensamblado recopilable, pero esto amplía la duración del ensamblado al que se hace referencia a la duración del ensamblado que hace referencia.

- **Interoperabilidad COM** No se pueden definir interfaces COM dentro de un ensamblado recopilable, ni ninguna instancia de tipos de un ensamblado recopilable se puede convertir en objetos COM. Un tipo de un ensamblado recopilable no puede actuar como contenedor CCW ni contenedor RCW. Pero los tipos de los ensamblados recopilables pueden usar objetos que implementen interfaces COM.

- **Invocación de plataforma** Los métodos que tienen el atributo <xref:System.Runtime.InteropServices.DllImportAttribute> no se compilan cuando se declaran en un ensamblado recopilable. La instrucción <xref:System.Reflection.Emit.OpCodes.Calli?displayProperty=nameWithType> no se puede usar en la implementación de un tipo de un ensamblado recopilable, y estos tipos no se pueden serializar en código no administrado. Pero se puede llamar al código nativo mediante el uso de un punto de entrada declarado en un ensamblado no recopilable.

- **Serialización** No se pueden serializar los objetos (en particular, los delegados) definidos en ensamblados recopilables. Se trata de una restricción para todos los tipos transitorios emitidos.

- **Carga de ensamblados** La emisión de la reflexión es el único mecanismo admitido para cargar ensamblados recopilables. Los ensamblados cargados mediante cualquier otra forma de carga de ensamblados no se pueden descargar.

- **Objetos enlazados por contexto** No se admiten las variables estáticas de contexto. Los tipos de un ensamblado recopilable no pueden extender <xref:System.ContextBoundObject>. Pero el código de los ensamblados recopilables puede usar objetos enlazados a un contexto definidos en otro lugar.

- **Datos estáticos de subproceso** No se admiten las variables estáticas de subproceso.

## <a name="see-also"></a>Vea también

- [Emitir métodos y ensamblados dinámicos](emitting-dynamic-methods-and-assemblies.md)
