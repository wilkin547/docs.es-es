---
title: "Enhancing Debugging with the Debugger Display Attributes | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "debugger, display attributes"
  - "DebuggerTypeProxyAttribute attribute"
  - "debugging [.NET Framework], debugger display attributes"
  - "DebuggerDisplayAttribute attribute"
  - "display attributes for debugger"
  - "DebuggerBrowsableAttribute attribute"
ms.assetid: 72bb7aa9-459b-42c4-9163-9312fab4c410
caps.latest.revision: 7
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 7
---
# Enhancing Debugging with the Debugger Display Attributes
Los atributos de presentación del depurador permiten al desarrollador del tipo, que especifica y mejor comprende el comportamiento en tiempo de ejecución de ese tipo, especificar el aspecto que tendrá ese tipo cuando se muestre en un depurador.  Además, los atributos de presentación del depurador que proporcionan una propiedad `Target` pueden aplicarlos en el nivel de ensamblado los usuarios sin necesidad de conocer el código fuente.  El atributo <xref:System.Diagnostics.DebuggerDisplayAttribute> controla la forma en que se muestra un tipo o un miembro en las ventanas de variables del depurador.  El atributo <xref:System.Diagnostics.DebuggerBrowsableAttribute> determina si se muestra y cómo lo hace un campo o una propiedad en las ventanas de variables del depurador.  El atributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> especifica un tipo de suplente, o un servidor proxy, para un tipo y cambia la manera en que se muestra el tipo en ventanas de depurador.  Cuando se ve una variable que tiene un servidor proxy, o un tipo suplente, el servidor proxy reemplaza el tipo original en la ventana de presentación del depurador**.** En la ventana de las variables del depuradorse muestran sólo los miembros públicos del tipo de servidor proxy.  No se muestran los miembros privados.  
  
## Utilizar DebuggerDisplayAttribute  
 El constructor <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A> tiene un solo argumento: una cadena que se debe mostrar en la columna de valores de las instancias del tipo.  Esta cadena puede contener llaves \({ y }\).  El texto incluido dentro de un par de llaves se evalúa como una expresión.  Por ejemplo, el siguiente código de C\# hace que se muestre "Count \= 4" cuando se selecciona el signo más \(\+\) para expandir la presentación del depurador para una instancia de `MyHashtable`.  
  
```  
[DebuggerDisplay("Count = {count}")]  
class MyHashtable  
{  
    public int count = 4;  
}  
```  
  
 No se procesan los atributos aplicados a propiedades a las que se hace referencia en la expresión.  Para el compilador de C\#, se permite una expresión general que sólo tiene acceso implícito a esta referencia para la instancia actual del tipo de destino.  La expresión es limitada; no tiene acceso a los alias, variables locales ni punteros.  En el código de C\#, puede usar una expresión general entre las llaves que tenga acceso implícito al puntero `this` sólo para la instancia actual del tipo de destino.  
  
 Por ejemplo, si un objeto de C\# tiene un `ToString()` reemplazado, el depurador llamará al reemplazo y mostrará su resultado en lugar del `{<typeName>}.` estándar. Por consiguiente, si ha reemplazado `ToString()`, no necesita utilizar <xref:System.Diagnostics.DebuggerDisplayAttribute>.  Si utiliza ambos, el atributo <xref:System.Diagnostics.DebuggerDisplayAttribute> tiene prioridad sobre el reemplazo de `ToString()`.  
  
## Utilizar DebuggerBrowsableAttribute  
 Aplique el atributo <xref:System.Diagnostics.DebuggerBrowsableAttribute> a un campo o propiedad para especificar cómo se debe mostrar el campo o la propiedad en la ventana del depurador.  El constructor de este atributo toma uno de los valores de enumeración <xref:System.Diagnostics.DebuggerBrowsableState>, que especifica uno de los estados siguientes:  
  
-   <xref:System.Diagnostics.DebuggerBrowsableState> indica que el miembro no se muestra en la ventana de datos.  Por ejemplo, cuando se utiliza este valor para <xref:System.Diagnostics.DebuggerBrowsableAttribute> en un campo, se quita el campo de la jerarquía; no se muestra el campo cuando se expande el tipo haciendo clic en el signo más \(\+\) correspondiente a la instancia de tipo.  
  
-   <xref:System.Diagnostics.DebuggerBrowsableState> indica que se muestra el miembro pero que no se expande de manera predeterminada.  Éste es el comportamiento predeterminado.  
  
-   <xref:System.Diagnostics.DebuggerBrowsableState> indica que no se muestra el propio miembro, sino que se muestran los objetos que lo constituyen si es una matriz o colección.  
  
> [!NOTE]
>  Visual Basic no admite el atributo <xref:System.Diagnostics.DebuggerBrowsableAttribute> en la versión 2.0 de .NET Framework.  
  
 El ejemplo de código siguiente muestra el uso de <xref:System.Diagnostics.DebuggerBrowsableAttribute> para impedir que en la ventana de depuración de la clase aparezca la propiedad situada a continuación.  
  
```  
[DebuggerBrowsable(DebuggerBrowsableState.Never)]  
public static string y = "Test String";  
```  
  
## Utilizar DebuggerTypeProxy  
 Utilice el atributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> cuando sea necesario cambiar significativa y fundamentalmente la vista de depuración de un tipo, pero no cambie el tipo en sí.  El atributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> se utiliza para especificar un servidor proxy de presentación para un tipo, permitiendo que los desarrolladores personalicen la vista del tipo.  Este atributo, como <xref:System.Diagnostics.DebuggerDisplayAttribute>, se puede usar en el nivel de ensamblado, en cuyo caso la propiedad <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A> especifica el tipo para el que se utilizará el servidor proxy.  El uso recomendado es que este atributo especifica un tipo anidado privado que aparece dentro del tipo al que se aplica el atributo.  Un evaluador de expresiones que admite los visores de tipo comprueba la existencia de este atributo cuando se muestra un tipo.  Si se encuentra el atributo, el evaluador de expresiones sustituye el tipo de servidor proxy de presentación para el tipo al que se aplica el atributo.  
  
 Cuando está presente el atributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, en la ventana de las variables del depurador se muestran únicamente los miembros públicos del tipo de servidor proxy.  No se muestran los miembros privados.  Vistas mejoradas por atributos no cambian el comportamiento de la ventana de datos.  
  
 Para evitar pérdidas de rendimiento innecesarias, los atributos del servidor proxy de presentación no se procesan hasta que se expande el objeto, ya sea haciendo clic en el signo más \(\+\) que aparece junto al tipo en una ventana de datos, ya a través de la aplicación del atributo <xref:System.Diagnostics.DebuggerBrowsableAttribute>.  Por consiguiente, se recomienda no aplicar ningún atributo al tipo de presentación.  Los atributos pueden y deben utilizarse en el cuerpo del tipo de presentación.  
  
 El ejemplo de código siguiente muestra el uso de <xref:System.Diagnostics.DebuggerTypeProxyAttribute> para especificar un tipo que se va a utilizar como un servidor proxy de presentación de depurador.  
  
```  
  
[DebuggerTypeProxy(typeof(HashtableDebugView))]  
class MyHashtable : Hashtable  
{  
    private const string TestString =   
        "This should not appear in the debug window.";  
  
    internal class HashtableDebugView  
    {  
        private Hashtable hashtable;  
        public const string TestStringProxy =   
            "This should appear in the debug window.";  
  
        // The constructor for the type proxy class must have a   
        // constructor that takes the target type as a parameter.  
        public HashtableDebugView(Hashtable hashtable)  
        {  
            this.hashtable = hashtable;  
        }  
    }  
}  
```  
  
## Ejemplo  
  
### Descripción  
 El ejemplo de código siguiente se puede ver en [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] para observar los resultados de aplicar los atributos <xref:System.Diagnostics.DebuggerDisplayAttribute>, <xref:System.Diagnostics.DebuggerBrowsableAttribute> y <xref:System.Diagnostics.DebuggerTypeProxyAttribute>.  
  
### Código  
 [!code-cpp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/cpp/program.cpp#1)]
 [!code-csharp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/CS/program.cs#1)]
 [!code-vb[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/VB/module1.vb#1)]  
  
## Vea también  
 <xref:System.Diagnostics.DebuggerDisplayAttribute>   
 <xref:System.Diagnostics.DebuggerBrowsableAttribute>   
 <xref:System.Diagnostics.DebuggerTypeProxyAttribute>