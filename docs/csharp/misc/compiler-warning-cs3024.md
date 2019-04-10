---
title: Advertencia del compilador CS3024
ms.date: 07/20/2015
f1_keywords:
- CS3024
helpviewer_keywords:
- CS3024
ms.assetid: fef9db31-9a7f-42d5-ad37-3e7faf661f95
ms.openlocfilehash: 7515fdd7bc8f57890e3f1aac6303ed4607cc2249
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59297298"
---
# <a name="compiler-warning-cs3024"></a>Advertencia del compilador CS3024
El tipo de restricción 'tipo' no es conforme a CLS  
  
 El compilador emite esta advertencia porque el uso de un tipo conforme a CLS como una restricción de tipo genérico puede hacer que sea imposible que código escrito en algunos lenguajes pueda usar la clase genérica.  
  
### <a name="to-eliminate-this-warning"></a>Para eliminar esta advertencia  
  
1. Use un tipo conforme a CLS para la restricción de tipo.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente genera el error CS3024 en varias ubicaciones:  
  
```csharp  
// cs3024.cs  
// Compile with: /target:library  
 [assembly: System.CLSCompliant(true)]  
  
[type: System.CLSCompliant(false)]  
public class TestClass // CS3024  
{  
    public ushort us;  
}  
[type: System.CLSCompliant(false)]  
public interface ITest // CS3024  
{}  
public interface I<T> where T : TestClass  
{}  
public class TestClass_2<T> where T : ITest  
{}  
public class TestClass_3<T> : I<T> where T : TestClass  
{}  
public class TestClass_4<T> : TestClass_2<T> where T : ITest  
{}  
public class Test  
{  
    public static int Main()  
    {  
        return 0;  
    }  
}  
```  
  
## <a name="see-also"></a>Vea también

- [Restricciones de tipos de parámetros](../../csharp/programming-guide/generics/constraints-on-type-parameters.md)
