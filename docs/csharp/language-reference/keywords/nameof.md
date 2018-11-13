---
title: nameof (Referencia de C#)
ms.date: 06/16/2017
f1_keywords:
- nameof_CSharpKeyword
- nameof
ms.assetid: 33601bf3-cc2c-4496-846d-f9679bccf2a7
ms.openlocfilehash: 01c87f8d63264aa342b04b8d3fcfc7e6f38db44b
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "50744377"
---
# <a name="nameof-c-reference"></a>nameof (Referencia de C#)

Se utiliza para obtener el nombre de cadena (incompleto) simple de una variable, tipo o miembro.  

Al informar de errores en el código, enlazar vínculos de controlador de vistas de modelo (MVC), desencadenar eventos de propiedad cambiada, etc., a menudo le interesa capturar el nombre de cadena de un método.  Usar `nameof` ayuda a lograr que su código siga siendo válido al cambiar el nombre de definiciones.  Antes había que usar literales de cadena para hacer referencia a definiciones, lo que resulta precario al cambiar el nombre de elementos de código, ya que las herramientas no saben comprobar estos literales de cadena.  
  
 Una expresión `nameof` tiene este formato:  
  
```csharp  
if (x == null) throw new ArgumentNullException(nameof(x));  
WriteLine(nameof(person.Address.ZipCode)); // prints "ZipCode"  
```  
  
## <a name="key-use-cases"></a>Casos de uso clave  
 Estos ejemplos muestran los casos de uso clave para `nameof`.  
  
 Validar parámetros:  
 ```csharp  
void f(string s) {  
    if (s == null) throw new ArgumentNullException(nameof(s));  
}  
```  
  
 Vínculos de acción de MVC:  
 ```html  
<%= Html.ActionLink("Sign up",  
             @typeof(UserController),  
             @nameof(UserController.SignUp))  
%>  
```  
  
 INotifyPropertyChanged:  
 ```csharp  
int p {  
    get { return this.p; }  
    set { this.p = value; PropertyChanged(this, new PropertyChangedEventArgs(nameof(this.p)); } // nameof(p) works too  
}  
```  
  
 Propiedad de dependencia de XAML:  
 ```csharp  
public static DependencyProperty AgeProperty = DependencyProperty.Register(nameof(Age), typeof(int), typeof(C));  
```  
  
 Registro:  
 ```csharp  
void f(int i) {  
    Log(nameof(f), "method entry");  
}  
```  
  
 Atributos:  
 ```csharp  
[DebuggerDisplay("={" + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```  
  
## <a name="examples"></a>Ejemplos  
 Algunos ejemplos de C#:  
  
```csharp  
using Stuff = Some.Cool.Functionality  
class C {  
    static int Method1 (string x, int y) {}  
    static int Method1 (string x, string y) {}  
    int Method2 (int z) {}  
    string f<T>() => nameof(T);  
}  
  
var c = new C()  
  
class Test {  
    static void Main (string[] args) {  
        Console.WriteLine(nameof(C)); // -> "C"  
        Console.WriteLine(nameof(C.Method1)); // -> "Method1"   
        Console.WriteLine(nameof(C.Method2)); // -> "Method2"  
        Console.WriteLine(nameof(c.Method1)); // -> "Method1"   
        Console.WriteLine(nameof(c.Method2)); // -> "Method2"  
        // Console.WriteLine(nameof(z)); -> "z" [inside of Method2 ok, inside Method1 is a compiler error]  
        Console.WriteLine(nameof(Stuff)); // -> "Stuff"  
        // Console.WriteLine(nameof(T)); -> "T" [works inside of method but not in attributes on the method]  
        Console.WriteLine(nameof(f)); // -> "f"  
        // Console.WriteLine(nameof(f<T>)); -> [syntax error]  
        // Console.WriteLine(nameof(f<>)); -> [syntax error]  
        // Console.WriteLine(nameof(Method2())); -> [error "This expression does not have a name"]  
    }
}
```  
  
## <a name="remarks"></a>Comentarios  
 El argumento `nameof` debe ser un nombre sencillo, nombre completo, acceso a miembros, acceso base a un miembro especificado o este acceso a un miembro especificado.  La expresión de argumento identifica una definición de código, pero nunca se evalúa.  
  
 Dado que el argumento debe ser sintácticamente una expresión, hay muchas cosas no permitidas que no sería útil mostrar.  Sí vale la pena mencionar los siguientes elementos que producen errores: tipos predefinidos (por ejemplo, `int` o `void`), tipos que aceptan valores null (`Point?`), tipos de matriz (`Customer[,]`), tipos de puntero (`Buffer*`), alias completo (`A::B`), tipos genéricos sin enlazar (`Dictionary<,>`), símbolos de preprocesamiento (`DEBUG`) y etiquetas (`loop:`).  
  
 Si necesita obtener el nombre completo, puede utilizar la expresión `typeof` junto con `nameof`.  Por ejemplo:
```csharp  
class C {
    void f(int i) {  
        Log($"{typeof(C)}.{nameof(f)}", "method entry");  
    }
}
``` 

 `typeof` no es una expresión constante como `nameof`, por lo que `typeof` no puede usarse junto con `nameof` en los mismos lugares que `nameof`.  Por ejemplo, el siguiente ejemplo provocaría un error de compilación CS0182:
 ```csharp  
[DebuggerDisplay("={" + typeof(C) + nameof(GetString) + "()}")]  
class C {  
    string GetString() { }  
}  
```    
 En los ejemplos verá que puede utilizar un nombre de tipo y acceder a un nombre de método de instancia.  No es necesario tener una instancia del tipo, tal como se requiere en las expresiones evaluadas.  Usar el nombre de tipo puede ser muy práctico en algunas situaciones, y puesto que solo hace referencia al nombre y no utiliza datos de instancia, no necesita idear una expresión o una variable de instancia.  
  
 Puede hacer referencia a los miembros de una clase en expresiones de atributos en la clase.  
  
 No hay ninguna manera de obtener información de firma, como "`Method1 (str, str)`".  Una manera de hacerlo es usar una expresión, `Expression e = () => A.B.Method1("s1", "s2")`, y extraer el MemberInfo del árbol de expresión resultante.  
  
## <a name="language-specifications"></a>Especificaciones del lenguaje  

Para obtener más información, vea la sección [Expresiones nameof](~/_csharplang/spec/expressions.md#nameof-expressions) de la [Especificación del lenguaje C#](../language-specification/index.md). La especificación del lenguaje es la fuente definitiva de la sintaxis y el uso de C#.
 
## <a name="see-also"></a>Vea también

- [Referencia de C#](../../../csharp/language-reference/index.md)  
- [Guía de programación de C#](../../../csharp/programming-guide/index.md)  
- [typeof](../../../csharp/language-reference/keywords/typeof.md)  
