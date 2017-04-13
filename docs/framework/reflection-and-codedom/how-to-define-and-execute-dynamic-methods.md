---
title: "How to: Define and Execute Dynamic Methods | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "reflection emit, dynamic methods"
  - "dynamic methods"
ms.assetid: 07d08a99-62c5-4254-bce2-2a75e55a18ab
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# How to: Define and Execute Dynamic Methods
Los procedimientos siguientes muestran cómo definir y ejecutar un método dinámico simple y un método dinámico enlazados a una instancia de una clase.  Para obtener más información sobre métodos dinámicos, vea la clase <xref:System.Reflection.Emit.DynamicMethod> y los [Escenarios métodos dinámicos de emisión de reflexión](http://msdn.microsoft.com/es-es/7c27ea3d-0f24-4bf3-8ceb-f49d33faca5e).  
  
### Para definir y ejecutar un método dinámico  
  
1.  Declare un tipo de delegado para ejecutar el método.  Plantéese utilizar un delegado genérico para minimizar el número de tipos de delegado que es necesario declarar.  El código siguiente declara dos tipos de delegado que se podrían utilizar para el método `SquareIt`, siendo uno de ellos genérico.  
  
     [!code-cpp[DynamicMethodHowTo#2](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#2)]
     [!code-csharp[DynamicMethodHowTo#2](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#2)]
     [!code-vb[DynamicMethodHowTo#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#2)]  
  
2.  Cree una matriz que especifique los tipos de parámetro para el método dinámico.  En este ejemplo, el único parámetro es `int` \(`Integer` en Visual Basic\), por lo que la matriz sólo tiene un elemento.  
  
     [!code-cpp[DynamicMethodHowTo#3](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#3)]
     [!code-csharp[DynamicMethodHowTo#3](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#3)]
     [!code-vb[DynamicMethodHowTo#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#3)]  
  
3.  Cree un control <xref:System.Reflection.Emit.DynamicMethod>.  En este ejemplo, el método se denomina `SquareIt`.  
  
    > [!NOTE]
    >  No es necesario proporcionar los nombres de los métodos dinámicos y no se pueden invocar por su nombre.  Puede haber varios métodos dinámicos con el mismo nombre.  Sin embargo, el nombre aparece en pilas de llamadas y puede ser útil a efectos de depuración.  
  
     El tipo del valor devuelto se especifica como `long`.  El método se asocia al módulo que contiene la clase `Example`, que contiene el código de ejemplo.  Se podría especificar cualquier módulo cargado.  El método dinámico actúa como un método `static` \(`Shared` en Visual Basic\) de nivel de módulo.  
  
     [!code-cpp[DynamicMethodHowTo#4](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#4)]
     [!code-csharp[DynamicMethodHowTo#4](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#4)]
     [!code-vb[DynamicMethodHowTo#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#4)]  
  
4.  Emita el cuerpo del método.  En este ejemplo, se utiliza un objeto <xref:System.Reflection.Emit.ILGenerator> para emitir el Lenguaje intermedio de Microsoft \(MSIL\).  Como alternativa, se puede usar un objeto <xref:System.Reflection.Emit.DynamicILInfo> junto con los generadores de código no administrado para emitir el cuerpo del método de un método <xref:System.Reflection.Emit.DynamicMethod>.  
  
     El código MSIL de este ejemplo carga el argumento, que es un valor `int`, en la pila, lo convierte en un valor `long`, duplica dicho valor `long` y multiplica ambos números.  Así se deja el resultado cuadrado en la pila y lo único que tiene que hacer el método es volver.  
  
     [!code-cpp[DynamicMethodHowTo#5](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#5)]
     [!code-csharp[DynamicMethodHowTo#5](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#5)]
     [!code-vb[DynamicMethodHowTo#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#5)]  
  
5.  Cree una instancia del delegado \(declarado en el paso 1\) que representa el método dinámico llamando al método <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A>.  Al crear el delegado, se finaliza el método y se omite cualquier intento posterior de cambiar el método \(por ejemplo, agregando más código MSIL\).  El código siguiente crea el delegado y lo invoca utilizando un delegado genérico.  
  
     [!code-cpp[DynamicMethodHowTo#6](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#6)]
     [!code-csharp[DynamicMethodHowTo#6](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#6)]
     [!code-vb[DynamicMethodHowTo#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#6)]  
  
### Para definir y ejecutar un método dinámico enlazado a un objeto  
  
1.  Declare un tipo de delegado para ejecutar el método.  Plantéese utilizar un delegado genérico para minimizar el número de tipos de delegado que es necesario declarar.  El método siguiente declara un tipo de delegado genérico que se puede utilizar para ejecutar cualquier método con un parámetro y un valor devuelto, o un método con dos parámetros y un valor devuelto si el delegado está enlazado a un objeto.  
  
     [!code-cpp[DynamicMethodHowTo#12](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#12)]
     [!code-csharp[DynamicMethodHowTo#12](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#12)]
     [!code-vb[DynamicMethodHowTo#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#12)]  
  
2.  Cree una matriz que especifique los tipos de parámetro para el método dinámico.  Si el delegado que representa al método se debe enlazar a un objeto, el primer parámetro debe ser del tipo del delegado al que está enlazado.  En este ejemplo hay dos parámetros, de los tipos `Example` e `int` \(`Integer` en Visual Basic\).  
  
     [!code-cpp[DynamicMethodHowTo#13](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#13)]
     [!code-csharp[DynamicMethodHowTo#13](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#13)]
     [!code-vb[DynamicMethodHowTo#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#13)]  
  
3.  Cree un control <xref:System.Reflection.Emit.DynamicMethod>.  En este ejemplo, el método no tiene nombre.  El tipo del valor devuelto está especificado como `int` \(`Integer` en Visual Basic\).  El método tiene acceso a los miembros privados y protegidos de la clase `Example`.  
  
     [!code-cpp[DynamicMethodHowTo#14](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#14)]
     [!code-csharp[DynamicMethodHowTo#14](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#14)]
     [!code-vb[DynamicMethodHowTo#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#14)]  
  
4.  Emita el cuerpo del método.  En este ejemplo, se utiliza un objeto <xref:System.Reflection.Emit.ILGenerator> para emitir el Lenguaje intermedio de Microsoft \(MSIL\).  Como alternativa, se puede usar un objeto <xref:System.Reflection.Emit.DynamicILInfo> junto con los generadores de código no administrado para emitir el cuerpo del método de un método <xref:System.Reflection.Emit.DynamicMethod>.  
  
     El código MSIL de este ejemplo carga el primer argumento, que es una instancia de la clase `Example`, y lo utiliza para cargar el valor de un campo de instancia privada del tipo `int`.  Se carga el segundo argumento y se multiplican los dos números.  Si el resultado es mayor que `int`, se trunca el valor y se descartan los bits más significativos.  El método vuelve, con el valor devuelto en la pila.  
  
     [!code-cpp[DynamicMethodHowTo#15](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#15)]
     [!code-csharp[DynamicMethodHowTo#15](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#15)]
     [!code-vb[DynamicMethodHowTo#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#15)]  
  
5.  Cree una instancia del delegado \(declarado en el paso 1\) que representa el método dinámico llamando a la sobrecarga del método <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%28System.Type%2CSystem.Object%29>.  Al crear el delegado, se finaliza el método y se omite cualquier intento posterior de cambiar el método \(por ejemplo, agregando más código MSIL\).  
  
    > [!NOTE]
    >  Puede llamar varias veces al método <xref:System.Reflection.Emit.DynamicMethod.CreateDelegate%2A> para crear delegados enlazados a otras instancias del tipo de destino.  
  
     El siguiente código enlaza el método a una nueva instancia de la clase `Example` cuyo campo de prueba privado está establecido en 42.  Es decir, cada vez que se invoca el delegado, se pasa la instancia de `Example` al primer parámetro del método.  
  
     Se utiliza el delegado `OneParameter` porque el primer parámetro del método siempre recibe la instancia de `Example`.  Cuando se invoca el delegado, sólo se requiere el segundo parámetro.  
  
     [!code-cpp[DynamicMethodHowTo#16](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#16)]
     [!code-csharp[DynamicMethodHowTo#16](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#16)]
     [!code-vb[DynamicMethodHowTo#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#16)]  
  
## Ejemplo  
 El ejemplo de código siguiente muestra un método dinámico simple y un método dinámico enlazado a una instancia de una clase.  
  
 El método dinámico simple toma un argumento, un entero de 32 bits, y devuelve el cuadrado ese entero en 64 bits.  Para invocar el método se utiliza un delegado genérico.  
  
 El segundo método dinámico tiene dos parámetros, de tipo `Example` y tipo `int` \(`Integer` en Visual Basic\).  Cuando se haya creado el método dinámico, estará enlazado a una instancia de `Example` usando un delegado genérico que tiene un argumento de tipo `int`.  El delegado no tiene un argumento de tipo `Example` porque el primer parámetro del método siempre recibe la instancia enlazada de `Example`.  Cuando se invoca el delegado, sólo se proporciona el argumento `int`.  Este método dinámico tiene acceso a un campo privado de la clase `Example` y devuelve el producto del campo privado y el argumento `int`.  
  
 El ejemplo de código define delegados que se pueden utilizar para ejecutar los métodos.  
  
 [!code-cpp[DynamicMethodHowTo#1](../../../samples/snippets/cpp/VS_Snippets_CLR/DynamicMethodHowTo/cpp/source.cpp#1)]
 [!code-csharp[DynamicMethodHowTo#1](../../../samples/snippets/csharp/VS_Snippets_CLR/DynamicMethodHowTo/cs/source.cs#1)]
 [!code-vb[DynamicMethodHowTo#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/DynamicMethodHowTo/vb/source.vb#1)]  
  
## Compilar el código  
  
-   El código contiene las instrucciones `using` de C\# \(`Imports` en Visual Basic\) necesarias para la compilación.  
  
-   No se requiere ninguna referencia de ensamblado adicional.  
  
-   Compile el código de la línea de comandos mediante csc.exe, vbc.exe, o cl.exe.  Para compilar el código en Visual Studio, póngalo en una plantilla de proyecto de aplicación de consola.  
  
## Vea también  
 <xref:System.Reflection.Emit.DynamicMethod>   
 [Utilizar la emisión de la reflexión](http://msdn.microsoft.com/es-es/ccc6540d-0e2c-4d89-b456-eb7353f9e9ac)   
 [Escenarios métodos dinámicos de emisión de reflexión](http://msdn.microsoft.com/es-es/7c27ea3d-0f24-4bf3-8ceb-f49d33faca5e)