---
title: Arquitectura y diseño
ms.date: 03/30/2017
ms.assetid: bd738d39-00e2-4bab-b387-90aac1a014bd
ms.openlocfilehash: 5a0d8aac401a3485bc5f158bcda893ad9ab424e8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43530475"
---
# <a name="architecture-and-design"></a><span data-ttu-id="9b3ca-102">Arquitectura y diseño</span><span class="sxs-lookup"><span data-stu-id="9b3ca-102">Architecture and Design</span></span>
<span data-ttu-id="9b3ca-103">El módulo de generación de SQL en el [proveedor de ejemplo](https://go.microsoft.com/fwlink/?LinkId=180616) se implementa como un visitante en el árbol de expresión que representa el árbol de comandos.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-103">The SQL generation module in the [Sample Provider](https://go.microsoft.com/fwlink/?LinkId=180616) is implemented as a visitor on the expression tree that represents the command tree.</span></span> <span data-ttu-id="9b3ca-104">La generación se realiza en un paso único al árbol de expresión.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-104">The generation is done in a single pass over the expression tree.</span></span>  
  
 <span data-ttu-id="9b3ca-105">Los nodos del árbol se procesan de abajo arriba.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-105">The nodes of the tree are processed from the bottom up.</span></span> <span data-ttu-id="9b3ca-106">Primero se genera una estructura intermedia, SqlSelectStatement o SqlBuilder, que implementan ISqlFragment.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-106">First, an intermediate structure is produced: SqlSelectStatement or SqlBuilder, both implementing ISqlFragment.</span></span> <span data-ttu-id="9b3ca-107">A continuación, la instrucción SQL de la cadena se genera a partir de esa estructura.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-107">Next, the string SQL statement is produced from that structure.</span></span> <span data-ttu-id="9b3ca-108">Hay dos motivos para la estructura intermedia:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-108">There are two reasons for the intermediate structure:</span></span>  
  
-   <span data-ttu-id="9b3ca-109">Lógicamente, una instrucción SQL SELECT se rellena de manera desordenada.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-109">Logically, a SQL SELECT statement is populated out of order.</span></span> <span data-ttu-id="9b3ca-110">Los nodos que participan en la cláusula FROM se visitan antes que los nodos que participan en las cláusulas WHERE, GROUP BY y ORDER BY.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-110">The nodes that participate in the FROM clause are visited before the nodes that participate in the WHERE, GROUP BY, and the ORDER BY clause.</span></span>  
  
-   <span data-ttu-id="9b3ca-111">Para cambiar el nombre de los alias, debe identificar todos los alias que se hayan utilizado para evitar colisiones durante el cambio de nombre.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-111">To rename aliases, you must identify all used aliases to avoid collisions during renaming.</span></span> <span data-ttu-id="9b3ca-112">Para aplazar las opciones de cambio de nombre en SqlBuilder, utilice objetos Symbol para representar las columnas candidatas al cambio de nombre.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-112">To defer the renaming choices in SqlBuilder, use Symbol objects to represent the columns that are candidates for renaming.</span></span>  
  
 <span data-ttu-id="9b3ca-113">![Diagrama](../../../../../docs/framework/data/adonet/ef/media/de1ca705-4f7c-4d2d-ace5-afefc6d3cefa.gif "de1ca705-4f7c-4d2d-ace5-afefc6d3cefa")</span><span class="sxs-lookup"><span data-stu-id="9b3ca-113">![Diagram](../../../../../docs/framework/data/adonet/ef/media/de1ca705-4f7c-4d2d-ace5-afefc6d3cefa.gif "de1ca705-4f7c-4d2d-ace5-afefc6d3cefa")</span></span>  
  
 <span data-ttu-id="9b3ca-114">En la primera fase, cuando se visita el árbol de expresión, las expresiones se agrupan en instrucciones SqlSelectStatement y se elimina la información de estructura jerárquica de las combinaciones y de los alias de combinación.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-114">In the first phase, while visiting the expression tree, expressions are grouped into SqlSelectStatements, joins are flattened, and join aliases are flattened.</span></span> <span data-ttu-id="9b3ca-115">Durante esta fase, los objetos Symbol representan columnas o alias de entrada a los que se puede cambiar el nombre.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-115">During this pass, Symbol objects represent columns or input aliases that may be renamed.</span></span>  
  
 <span data-ttu-id="9b3ca-116">En la segunda fase, cuando se genera la cadena real, se cambia el nombre de los alias.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-116">In the second phase, while producing the actual string, aliases are renamed.</span></span>  
  
## <a name="data-structures"></a><span data-ttu-id="9b3ca-117">Estructuras de datos</span><span class="sxs-lookup"><span data-stu-id="9b3ca-117">Data Structures</span></span>  
 <span data-ttu-id="9b3ca-118">Esta sección describen los tipos utilizados en el [proveedor de ejemplo](https://go.microsoft.com/fwlink/?LinkId=180616) que usa para crear una instrucción SQL.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-118">This section discusses the types used in the [Sample Provider](https://go.microsoft.com/fwlink/?LinkId=180616) that you use to build a SQL statement.</span></span>  
  
### <a name="isqlfragment"></a><span data-ttu-id="9b3ca-119">ISqlFragment</span><span class="sxs-lookup"><span data-stu-id="9b3ca-119">ISqlFragment</span></span>  
 <span data-ttu-id="9b3ca-120">Esta sección abarca las clases que implementan la interfaz ISqlFragment, que sirve para dos fines:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-120">This section covers the classes that implement the ISqlFragment interface, which serves two purposes:</span></span>  
  
-   <span data-ttu-id="9b3ca-121">Un tipo de valor devuelto común para todos los métodos de visitante.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-121">A common return type for all the visitor methods.</span></span>  
  
-   <span data-ttu-id="9b3ca-122">Proporciona un método para escribir la cadena de SQL final.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-122">Gives a method to write the final SQL string.</span></span>  
  
```  
internal interface ISqlFragment {  
   void WriteSql(SqlWriter writer, SqlGenerator sqlGenerator);  
}  
```  
  
#### <a name="sqlbuilder"></a><span data-ttu-id="9b3ca-123">SqlBuilder</span><span class="sxs-lookup"><span data-stu-id="9b3ca-123">SqlBuilder</span></span>  
 <span data-ttu-id="9b3ca-124">SqlBuilder es un dispositivo de recopilación para la cadena de SQL final, similar a StringBuilder.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-124">SqlBuilder is a gathering device for the final SQL string, similar to StringBuilder.</span></span> <span data-ttu-id="9b3ca-125">Está compuesto de las cadenas que constituyen el SQL final, junto con objetos ISqlFragment que se pueden convertir en cadenas.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-125">It consists of the strings that make up the final SQL, along with ISqlFragments that can be converted into strings.</span></span>  
  
```  
internal sealed class SqlBuilder : ISqlFragment {  
   public void Append(object s)  
   public void AppendLine()  
   public bool IsEmpty  
}  
```  
  
#### <a name="sqlselectstatement"></a><span data-ttu-id="9b3ca-126">SqlSelectStatement</span><span class="sxs-lookup"><span data-stu-id="9b3ca-126">SqlSelectStatement</span></span>  
 <span data-ttu-id="9b3ca-127">SqlSelectStatement representa una instrucción SQL SELECT canónica de la forma "SELECT...</span><span class="sxs-lookup"><span data-stu-id="9b3ca-127">SqlSelectStatement represents a canonical SQL SELECT statement of the shape "SELECT …</span></span> <span data-ttu-id="9b3ca-128">DE..</span><span class="sxs-lookup"><span data-stu-id="9b3ca-128">FROM  ..</span></span> <span data-ttu-id="9b3ca-129">WHERE...</span><span class="sxs-lookup"><span data-stu-id="9b3ca-129">WHERE …</span></span> <span data-ttu-id="9b3ca-130">AGRUPAR POR...</span><span class="sxs-lookup"><span data-stu-id="9b3ca-130">GROUP BY …</span></span> <span data-ttu-id="9b3ca-131">SE ORDENA POR".</span><span class="sxs-lookup"><span data-stu-id="9b3ca-131">ORDER BY".</span></span>  
  
 <span data-ttu-id="9b3ca-132">Cada una de las cláusulas de SQL está representada por un objeto StringBuilder.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-132">Each of the SQL clauses is represented by a StringBuilder.</span></span> <span data-ttu-id="9b3ca-133">Además, realiza un seguimiento de si se ha especificado Distinct y si la instrucción se encuentra en el nivel más alto.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-133">In addition, it tracks whether Distinct has been specified and whether the statement is topmost.</span></span> <span data-ttu-id="9b3ca-134">Si la instrucción no se encuentra en el nivel más alto, la cláusula ORDER BY se omite, a menos que la instrucción también tenga una cláusula TOP.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-134">If the statement is not topmost, the ORDER BY clause is omitted unless the statement also has a TOP clause.</span></span>  
  
 <span data-ttu-id="9b3ca-135">FromExtents contiene la lista de entradas de la instrucción SELECT.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-135">FromExtents contains the list of inputs for the SELECT statement.</span></span> <span data-ttu-id="9b3ca-136">Normalmente, consta de un único elemento.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-136">There is usually just one element in this.</span></span> <span data-ttu-id="9b3ca-137">Las instrucciones SELECT de las combinaciones pueden tener temporalmente más de un elemento.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-137">SELECT statements for joins may temporarily have more than one element.</span></span>  
  
 <span data-ttu-id="9b3ca-138">Si un nodo Join crea la instrucción SELECT, SqlSelectStatement mantiene una lista de todas las extensiones cuya información de estructura jerárquica se ha eliminado en la combinación en AllJoinExtents.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-138">If the SELECT statement is created by a Join node, SqlSelectStatement maintains a list of all the extents that have been flattened in the join in AllJoinExtents.</span></span> <span data-ttu-id="9b3ca-139">OuterExtents representa las referencias externas de la instrucción SqlSelectStatement y se utiliza para cambiar el nombre de los alias de entrada.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-139">OuterExtents represents outer references of the SqlSelectStatement and is used for input alias renaming.</span></span>  
  
```  
internal sealed class SqlSelectStatement : ISqlFragment {  
   internal bool IsDistinct { get, set };  
   internal bool IsTopMost  
  
   internal List<Symbol> AllJoinExtents { get, set };  
   internal List<Symbol> FromExtents { get};  
   internal Dictionary<Symbol, bool> OuterExtents { get};  
  
   internal TopClause Top { get, set };  
  
   internal SqlBuilder Select {get};  
   internal SqlBuilder From  
   internal SqlBuilder Where  
   internal SqlBuilder GroupBy  
   public SqlBuilder OrderBy  
}  
```  
  
#### <a name="topclause"></a><span data-ttu-id="9b3ca-140">TopClause</span><span class="sxs-lookup"><span data-stu-id="9b3ca-140">TopClause</span></span>  
 <span data-ttu-id="9b3ca-141">TopClause representa la expresión TOP en una instrucción SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-141">TopClause represents the TOP expression in a SqlSelectStatement.</span></span> <span data-ttu-id="9b3ca-142">La propiedad TopCount indica cuántas filas TOP deben seleccionarse.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-142">The TopCount property indicates how many TOP rows should be selected.</span></span>  <span data-ttu-id="9b3ca-143">Cuando el valor de la propiedad WithTies es true, la cláusula TopClause se generó a partir de una expresión DbLimitExpession.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-143">When WithTies is true, the TopClause was built from a DbLimitExpession.</span></span>  
  
```  
class TopClause : ISqlFragment {  
   internal bool WithTies {get}  
   internal ISqlFragment TopCount {get}  
   internal TopClause(ISqlFragment topCount, bool withTies)  
   internal TopClause(int topCount, bool withTies)  
}  
```  
  
### <a name="symbols"></a><span data-ttu-id="9b3ca-144">Símbolos</span><span class="sxs-lookup"><span data-stu-id="9b3ca-144">Symbols</span></span>  
 <span data-ttu-id="9b3ca-145">Las clases relacionadas con Symbol y la tabla de símbolos cambian el nombre a los alias de entrada, eliminan información de estructura jerárquica de los alias de combinación y cambian el nombre a los alias de columna.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-145">The Symbol-related classes and the symbol table perform input alias renaming, join alias flattening, and column alias renaming.</span></span>  
  
 <span data-ttu-id="9b3ca-146">La clase Symbol representa una extensión, una instrucción SELECT anidada o una columna.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-146">The Symbol class represents an extent, a nested SELECT statement, or a column.</span></span> <span data-ttu-id="9b3ca-147">Se utiliza en lugar de un alias real para permitir el cambio de nombre una vez utilizada y presenta también información adicional del artefacto que representa (como el tipo).</span><span class="sxs-lookup"><span data-stu-id="9b3ca-147">It is used instead of an actual alias to allow for renaming after it has been used and it also carries additional information for the artifact it represents (like the type).</span></span>  
  
```  
class Symbol : ISqlFragment {  
   internal Dictionary<string, Symbol> Columns {get}  
   internal bool NeedsRenaming {get, set}  
   internal bool IsUnnest {get, set}   //not used  
  
   public string Name{get}  
   public string NewName {get,set}  
   internal TypeUsage Type {get, set}  
  
   public Symbol(string name, TypeUsage type)  
}  
```  
  
 <span data-ttu-id="9b3ca-148">El nombre almacena el alias original de la extensión representada, la instrucción SELECT anidada o una columna.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-148">Name stores the original alias for the represented extent, nested SELECT statement, or a column.</span></span>  
  
 <span data-ttu-id="9b3ca-149">NewName almacena el alias que se utilizará en la instrucción SELECT de SQL.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-149">NewName stores the alias that will be used in the SQL SELECT statement.</span></span> <span data-ttu-id="9b3ca-150">Se establece originalmente en Name y solo se cambia el nombre si resulta necesario al generar la consulta de la cadena final.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-150">It is originally set to Name, and only renamed if needed when generating the final string query.</span></span>  
  
 <span data-ttu-id="9b3ca-151">El tipo solamente es útil para los símbolos que representan extensiones e instrucciones SELECT anidadas.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-151">Type is only useful for symbols representing extents and nested SELECT statements.</span></span>  
  
#### <a name="symbolpair"></a><span data-ttu-id="9b3ca-152">SymbolPair</span><span class="sxs-lookup"><span data-stu-id="9b3ca-152">SymbolPair</span></span>  
 <span data-ttu-id="9b3ca-153">La clase SymbolPair se encarga de la eliminación de la información de estructura jerárquica de los registros.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-153">The SymbolPair class addresses record flattening.</span></span>  
  
 <span data-ttu-id="9b3ca-154">Tomemos como ejemplo una expresión de propiedad D(v, "j3.j2.j1.a.x"), donde v es una VarRef, j1, j2, j3 son las combinaciones, a es una extensión y x es una columna.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-154">Consider a property expression D(v, "j3.j2.j1.a.x") where v is a VarRef, j1, j2, j3 are joins, a is an extent, and x is a columns.</span></span>  
  
 <span data-ttu-id="9b3ca-155">Esto tiene que ser traducido posteriormente a {j'}.{x'}.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-155">This has to be translated eventually into {j'}.{x'}.</span></span> <span data-ttu-id="9b3ca-156">El campo de origen representa la instrucción SqlStatement extrema, que representa una expresión de combinación (por ejemplo, j2); es siempre un símbolo Join.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-156">The source field represents the outermost SqlStatement, representing a join expression (say j2); this is always a Join symbol.</span></span> <span data-ttu-id="9b3ca-157">El campo de columna se mueve de un símbolo de combinación al siguiente hasta que se detiene en un símbolo que no es de combinación.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-157">The column field moves from one join symbol to the next until it stops at a non-join symbol.</span></span> <span data-ttu-id="9b3ca-158">Es lo que se devuelve cuando se visita una expresión DbPropertyExpression, pero nunca se agrega a un SqlBuilder.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-158">This is returned when visiting a DbPropertyExpression but is never added to a SqlBuilder.</span></span>  
  
```  
class SymbolPair : ISqlFragment {  
   public Symbol Source;  
   public Symbol Column;  
   public SymbolPair(Symbol source, Symbol column)  
}  
```  
  
#### <a name="joinsymbol"></a><span data-ttu-id="9b3ca-159">JoinSymbol</span><span class="sxs-lookup"><span data-stu-id="9b3ca-159">JoinSymbol</span></span>  
 <span data-ttu-id="9b3ca-160">Un símbolo Join es un objeto Symbol que representa una instrucción SELECT anidada con una combinación o una entrada de combinación.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-160">A Join symbol is a Symbol that represents a nested SELECT statement with a join or a join input.</span></span>  
  
```  
internal sealed class JoinSymbol : Symbol {  
   internal List<Symbol> ColumnList {get, set}  
   internal List<Symbol> ExtentList {get}  
   internal List<Symbol> FlattenedExtentList {get, set}  
   internal Dictionary<string, Symbol> NameToExtent {get}  
   internal bool IsNestedJoin {get, set}  
  
   public JoinSymbol(string name, TypeUsage type, List<Symbol> extents)  
}  
```  
  
 <span data-ttu-id="9b3ca-161">ColumnList representa la lista de columnas de la cláusula SELECT si este símbolo representa una instrucción SELECT de SQL.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-161">ColumnList represents the list of columns in the SELECT clause if this symbol represents a SQL SELECT statement.</span></span> <span data-ttu-id="9b3ca-162">ExtentList es la lista de extensiones de la cláusula SELECT.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-162">ExtentList is the list of extents in the SELECT clause.</span></span> <span data-ttu-id="9b3ca-163">Si la combinación tiene varias extensiones sin información de estructura jerárquica en el nivel superior, FlattenedExtentList realiza un seguimiento de las extensiones para asegurarse de que el nombre de los alias de extensión se cambia correctamente.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-163">If the join has multiple extents flattened at the top level, FlattenedExtentList tracks the extents to ensure that extent aliases are renamed correctly.</span></span>  
  
 <span data-ttu-id="9b3ca-164">NameToExtent tiene todas las extensiones de ExtentList como un diccionario.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-164">NameToExtent has all the extents in ExtentList as a dictionary.</span></span> <span data-ttu-id="9b3ca-165">IsNestedJoin se utiliza para determinar si JoinSymbol es un símbolo de combinación normal o un símbolo con una instrucción SqlSelectStatement correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-165">IsNestedJoin is used to determine whether a JoinSymbol is an ordinary join symbol or one that has a corresponding SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="9b3ca-166">Todas las listas se establecen una vez exactamente y después se utilizan para realizar búsquedas o para enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-166">All the lists are set exactly once and then used for lookups or enumeration.</span></span>  
  
#### <a name="symboltable"></a><span data-ttu-id="9b3ca-167">SymbolTable</span><span class="sxs-lookup"><span data-stu-id="9b3ca-167">SymbolTable</span></span>  
 <span data-ttu-id="9b3ca-168">SymbolTable se utiliza para resolver nombres de variable como símbolos.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-168">SymbolTable is used to resolve variable names to Symbols.</span></span> <span data-ttu-id="9b3ca-169">SymbolTable se implementa como una pila con una nueva entrada para cada ámbito.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-169">SymbolTable is implemented as a stack with a new entry for each scope.</span></span> <span data-ttu-id="9b3ca-170">Las búsquedas examinan la pila desde la parte superior a la parte inferior hasta que se encuentra una entrada.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-170">Lookups search from the top of the stack to the bottom until an entry is found.</span></span>  
  
```  
internal sealed class SymbolTable {  
   internal void EnterScope()  
   internal void ExitScope()  
   internal void Add(string name, Symbol value)  
   internal Symbol Lookup(string name)  
}  
```  
  
 <span data-ttu-id="9b3ca-171">Hay solo una tabla SymbolTable por instancia del módulo de generación de Sql.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-171">There is only one SymbolTable per one instance of the Sql Generation module.</span></span> <span data-ttu-id="9b3ca-172">Se entra y se sale de los ámbitos para cada nodo relacional.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-172">Scopes are entered and exited for each relational node.</span></span> <span data-ttu-id="9b3ca-173">Todos los símbolos de ámbitos anteriores están visibles para los ámbitos posteriores, a menos que estén ocultos por otros símbolos con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-173">All symbols in earlier scopes are visible to later scopes unless hidden by other symbols with the same name.</span></span>  
  
### <a name="global-state-for-the-visitor"></a><span data-ttu-id="9b3ca-174">Estado global para el visitante</span><span class="sxs-lookup"><span data-stu-id="9b3ca-174">Global State for the Visitor</span></span>  
 <span data-ttu-id="9b3ca-175">Para ayudar en el cambio de nombre de alias y columnas, mantenga una lista de todos los nombres de columna (AllColumnNames) y alias de extensión (AllExtentNames) utilizados en el primer paso al árbol de consultas.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-175">To assist in renaming of aliases and columns, maintain a list of all the column names (AllColumnNames) and extent aliases (AllExtentNames) that have been used in the first pass over the query tree.</span></span>  <span data-ttu-id="9b3ca-176">La tabla de símbolos resuelve los nombres de variable como símbolos.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-176">The symbol table resolves variable names to Symbols.</span></span> <span data-ttu-id="9b3ca-177">IsVarRefSingle solo se utiliza a efectos de comprobación, no es estrictamente necesario.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-177">IsVarRefSingle is only used for verification purposes, it is not strictly necessary.</span></span>  
  
 <span data-ttu-id="9b3ca-178">Las dos pilas utilizadas mediante CurrentSelectStatement e IsParentAJoin se utilizan para pasar los "parámetros" de los nodos primarios a los secundarios, puesto que el patrón del visitante no permite el paso de parámetros.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-178">The two stacks used via CurrentSelectStatement and IsParentAJoin are used to pass "parameters" from parent to child nodes, since the visitor pattern does not allow us to pass parameters.</span></span>  
  
```  
internal Dictionary<string, int> AllExtentNames {get}  
internal Dictionary<string, int> AllColumnNames {get}  
SymbolTable symbolTable = new SymbolTable();  
bool isVarRefSingle = false;  
  
Stack<SqlSelectStatement> selectStatementStack;  
private SqlSelectStatement CurrentSelectStatement{get}  
  
Stack<bool> isParentAJoinStack;  
private bool IsParentAJoin{get}  
```  
  
## <a name="common-scenarios"></a><span data-ttu-id="9b3ca-179">Escenarios comunes</span><span class="sxs-lookup"><span data-stu-id="9b3ca-179">Common Scenarios</span></span>  
 <span data-ttu-id="9b3ca-180">En esta sección se explican los escenarios de proveedor más habituales.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-180">This section discusses common provider scenarios.</span></span>  
  
### <a name="grouping-expression-nodes-into-sql-statements"></a><span data-ttu-id="9b3ca-181">Agrupar nodos de expresión en instrucciones SQL</span><span class="sxs-lookup"><span data-stu-id="9b3ca-181">Grouping Expression Nodes into SQL Statements</span></span>  
 <span data-ttu-id="9b3ca-182">Cuando se encuentra el primer nodo relacional (normalmente una extensión de DbScanExpression) al visitar el árbol de abajo arriba, se crea una instrucción SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-182">A SqlSelectStatement is created when the first relational node is encountered (typically a DbScanExpression extent) when visiting the tree from the bottom up.</span></span> <span data-ttu-id="9b3ca-183">Para generar una instrucción SELECT de SQL con el menor número de consultas anidadas posible, agregue tantos nodos primarios como sea posible en esa instrucción SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-183">To produce a SQL SELECT statement with as few nested queries as possible, aggregate as many of its parent nodes as possible in that SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="9b3ca-184">La decisión sobre si un determinado nodo (relacional) se puede agregar a la instrucción SqlSelectStatement actual (la que se devolvió al visitar la entrada) o si es necesario iniciar una nueva instrucción es calculada por el método IsCompatible y depende del contenido de la instrucción SqlSelectStatement, que depende, a su vez, de qué nodos estaban situados por debajo del nodo especificado.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-184">The decision of whether a given (relational) node can be added to the current SqlSelectStatement (the one returned when visiting the input) or if a new statement needs to be started is computed by the method IsCompatible and depends on what is already in the SqlSelectStatement, which depends on what nodes were below the given node.</span></span>  
  
 <span data-ttu-id="9b3ca-185">Normalmente, si las cláusulas de instrucciones SQL se evalúan después de las cláusulas en las que los nodos que se están considerando para la combinación no están vacíos, el nodo no se puede agregar a la instrucción actual.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-185">Typically, if SQL statement clauses are evaluated after clauses where the nodes being considered for merging are not empty, the node cannot be added to the current statement.</span></span> <span data-ttu-id="9b3ca-186">Por ejemplo, si el nodo siguiente es un objeto Filter, solo se podrá incorporar a la instrucción SqlSelectStatement actual si se cumple lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-186">For example, if the next node is a Filter, that node can be incorporated into the current SqlSelectStatement only if the following is true:</span></span>  
  
-   <span data-ttu-id="9b3ca-187">La lista SELECT está vacía.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-187">The SELECT list is empty.</span></span> <span data-ttu-id="9b3ca-188">Si no lo está, un nodo anterior al filtro generó la lista de selección y puede que el predicado haga referencia a las columnas generadas por esa lista SELECT.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-188">If the SELECT list is not empty, the select list was produced by a node preceding the filter and the predicate may refer to columns produced by that SELECT list.</span></span>  
  
-   <span data-ttu-id="9b3ca-189">GROUPBY está vacío.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-189">The GROUPBY is empty.</span></span> <span data-ttu-id="9b3ca-190">Si no lo está, agregar el filtro significaría que el filtrado se produciría antes que la agrupación, lo cual no es correcto.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-190">If the GROUPBY is not empty, adding the filter would mean filtering before grouping, which is not correct.</span></span>  
  
-   <span data-ttu-id="9b3ca-191">La cláusula TOP está vacía.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-191">The TOP clause is empty.</span></span> <span data-ttu-id="9b3ca-192">Si no lo está, agregar el filtro significaría que el filtrado se produciría antes que la ejecución de la cláusula TOP, lo cual no es correcto.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-192">If the TOP clause is not empty, adding the filter would mean filtering before doing TOP, which is not correct.</span></span>  
  
 <span data-ttu-id="9b3ca-193">Esto no se aplica a los nodos no relacionales, como DbConstantExpression, o a expresiones aritméticas, porque se incluyen siempre como parte de una instrucción SqlSelectStatement existente.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-193">This does not apply to non-relational nodes like DbConstantExpression or arithmetic expressions, because these are always included as part of an existing SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="9b3ca-194">Asimismo, al encontrar la raíz del árbol de combinaciones (un nodo de combinación que no tiene un elemento primario de combinación), se inicia una nueva instrucción SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-194">Also, when encountering the root of join tree (a join node that does not have a join parent), a new SqlSelectStatement is started.</span></span> <span data-ttu-id="9b3ca-195">Todos los elementos secundarios de combinación del lateral izquierdo se agregan a esa instrucción SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-195">All of its left spine join children are aggregated into that SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="9b3ca-196">Siempre que se inicia una instrucción SqlSelectStatement nueva, y la actual se agrega a la entrada, es posible que la instrucción SqlSelectStatement actual necesite completarse agregando columnas de proyección (una cláusula SELECT) si no existe una.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-196">Whenever a new SqlSelectStatement is started, and the current one is added to the input, the current SqlSelectStatement may need to be completed by adding projection columns (a SELECT clause) if one does not exist.</span></span> <span data-ttu-id="9b3ca-197">Esto se realiza con el método AddDefaultColumns, que examina la propiedad FromExtents de la instrucción SqlSelectStatement y agrega todas las columnas que la lista de extensiones representada por FromExtents introduce en el ámbito de la lista de columnas proyectadas.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-197">This is done with the method AddDefaultColumns, which looks at the FromExtents of the SqlSelectStatement and adds all the columns that the list of extents represented by FromExtents brings in scope to the list of projected columns.</span></span> <span data-ttu-id="9b3ca-198">El motivo de esto es porque en ese punto no se sabe a qué columnas hacen referencia los otros nodos.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-198">This is done, because at that point, it is unknown which columns are referenced by the other nodes.</span></span> <span data-ttu-id="9b3ca-199">Esto se puede optimizar para proyectar solo las columnas que se puedan utilizar después.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-199">This can be optimized to only project the columns that can later be used.</span></span>  
  
### <a name="join-flattening"></a><span data-ttu-id="9b3ca-200">Eliminación de la información de estructura jerárquica de las combinaciones</span><span class="sxs-lookup"><span data-stu-id="9b3ca-200">Join Flattening</span></span>  
 <span data-ttu-id="9b3ca-201">La propiedad IsParentAJoin ayuda a determinar si se puede quitar la información de estructura jerárquica de una determinada combinación.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-201">The IsParentAJoin property helps determine whether a given join can be flattened.</span></span> <span data-ttu-id="9b3ca-202">En particular, la propiedad IsParentAJoin solo devuelve `true` para el elemento secundario izquierdo de una combinación y para cada DbScanExpression que sea una entrada inmediata de una combinación, en cuyo caso ese nodo secundario vuelve a utilizar la misma instrucción SqlSelectStatement que el elemento primario utilizaría después.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-202">In particular, IsParentAJoin returns `true` only for the left child of a join and for each DbScanExpression that is an immediate input to a join, in which case that child node reuses the same SqlSelectStatement that the parent would later use.</span></span> <span data-ttu-id="9b3ca-203">Para obtener más información acerca de las expresiones, vea "Expresiones de combinación".</span><span class="sxs-lookup"><span data-stu-id="9b3ca-203">For more information, see "Join Expressions".</span></span>  
  
### <a name="input-alias-redirecting"></a><span data-ttu-id="9b3ca-204">Redirección de alias de entrada</span><span class="sxs-lookup"><span data-stu-id="9b3ca-204">Input Alias Redirecting</span></span>  
 <span data-ttu-id="9b3ca-205">La redirección de los alias de entrada se logra con la tabla de símbolos.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-205">Input alias redirecting is accomplished with the symbol table.</span></span>  
  
 <span data-ttu-id="9b3ca-206">Para explicar la redirección de alias de entrada, consulte el primer ejemplo de [generar SQL de árboles de comandos: procedimientos recomendados](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md).</span><span class="sxs-lookup"><span data-stu-id="9b3ca-206">To explain input alias redirecting, refer to the first example in [Generating SQL from Command Trees - Best Practices](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md).</span></span>  <span data-ttu-id="9b3ca-207">En él, "a" necesita redirigirse a "b" en la proyección.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-207">There "a" needed to be redirected to "b" in the projection.</span></span>  
  
 <span data-ttu-id="9b3ca-208">Cuando se crea un objeto SqlSelectStatement, la extensión que representa la entrada al nodo se coloca en la propiedad From del objeto SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-208">When a SqlSelectStatement object is created, the extent that is the input to the node is put in the From property of the SqlSelectStatement.</span></span> <span data-ttu-id="9b3ca-209">Se crea un objeto Symbol (<symbol_b>) basado en el nombre del enlace de entrada ("b") para representar esa extensión y se anexa "AS" + <symbol_b> a la cláusula From.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-209">A Symbol (<symbol_b>) is created based on the input binding name ("b") to represent that extent and "AS  " +  <symbol_b> is appended to the From Clause.</span></span>  <span data-ttu-id="9b3ca-210">El símbolo también se agrega a la propiedad FromExtents.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-210">The symbol is also added to the FromExtents property.</span></span>  
  
 <span data-ttu-id="9b3ca-211">El símbolo también se agrega a la tabla de símbolos para vincularle el nombre del enlace de entrada ("b", <symbol_b>).</span><span class="sxs-lookup"><span data-stu-id="9b3ca-211">The symbol is also added to the symbol table to link the input binding name to it ("b", <symbol_b>).</span></span>  
  
 <span data-ttu-id="9b3ca-212">Si un nodo posterior vuelve a utilizar esa instrucción SqlSelectStatement, agrega una entrada a la tabla de símbolos para vincular su nombre de enlace de entrada a ese símbolo.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-212">If a subsequent node reuses that SqlSelectStatement, it adds an entry to the symbol table to link its input binding name to that symbol.</span></span> <span data-ttu-id="9b3ca-213">En nuestro ejemplo, podría volver a usar la instrucción SqlSelectStatement y agregue la expresión DbProjectExpression con el nombre de enlace de entrada de "a" ("a", \< symbol_b >) a la tabla.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-213">In our example, the DbProjectExpression with the input binding name of "a" would reuse the SqlSelectStatement and add ("a", \< symbol_b>) to the table.</span></span>  
  
 <span data-ttu-id="9b3ca-214">Cuando las expresiones hacen referencia al nombre de enlace de entrada del nodo que está reutilizando la instrucción SqlSelectStatement, esa referencia se resuelve usando la tabla de símbolos como el símbolo redirigido correcto.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-214">When expressions reference the input binding name of the node that is reusing the SqlSelectStatement, that reference is resolved using the symbol table to the correct redirected symbol.</span></span> <span data-ttu-id="9b3ca-215">Cuando "a" de "a.x" se resuelva al visitar la expresión DbVariableReferenceExpression que representa "a", lo hará como el objeto Symbol <symbol_b>.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-215">When "a" from "a.x" is resolved while visiting the DbVariableReferenceExpression representing "a" it will resolve to the Symbol <symbol_b>.</span></span>  
  
### <a name="join-alias-flattening"></a><span data-ttu-id="9b3ca-216">Eliminación de la información de estructura jerárquica de los alias de combinación</span><span class="sxs-lookup"><span data-stu-id="9b3ca-216">Join Alias Flattening</span></span>  
 <span data-ttu-id="9b3ca-217">La eliminación de la información de estructura jerárquica de los alias de combinación se logra al visitar una expresión DbPropertyExpression, como se describe en la sección titulada DbPropertyExpression.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-217">Join alias flattening is achieved when visiting a DbPropertyExpression as described in the section titled DbPropertyExpression.</span></span>  
  
### <a name="column-name-and-extent-alias-renaming"></a><span data-ttu-id="9b3ca-218">Cambio de nombre de una columna y de un alias de extensión</span><span class="sxs-lookup"><span data-stu-id="9b3ca-218">Column Name and Extent Alias Renaming</span></span>  
 <span data-ttu-id="9b3ca-219">El problema del cambio de nombre de una columna y de un alias de extensión se resuelve utilizando símbolos que solo se sustituyen por alias en la segunda fase de la generación, como se describe en la sección titulada Segunda fase de la generación de SQL: Generar el comando String.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-219">The issue of column name and extent alias renaming is addressed by using symbols that only get substituted with aliases in the second phase of the generation described in the section titled Second Phase of SQL Generation: Generating the String Command.</span></span>  
  
## <a name="first-phase-of-the-sql-generation-visiting-the-expression-tree"></a><span data-ttu-id="9b3ca-220">Primera fase de la generación de SQL: Visitar el árbol de expresión</span><span class="sxs-lookup"><span data-stu-id="9b3ca-220">First Phase of the SQL Generation: Visiting the Expression Tree</span></span>  
 <span data-ttu-id="9b3ca-221">En esta sección se describe la primera fase de generación de SQL, cuando se visita la expresión que representa la consulta y se genera una estructura intermedia, SqlSelectStatement o SqlBuilder.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-221">This section describes the first phase of SQL generation, when the expression representing the query is visited and an intermediate structure is produced, either a SqlSelectStatement or a SqlBuilder.</span></span>  
  
 <span data-ttu-id="9b3ca-222">En esta sección se describen los principios de las visitas a las diferentes categorías de nodo de expresión y se ofrecen detalles sobre las visitas a determinados tipos de expresión.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-222">This section describes the principles of visiting different expression node categories, and details of visiting specific expression types.</span></span>  
  
### <a name="relational-non-join-nodes"></a><span data-ttu-id="9b3ca-223">Nodos relacionales (no de combinación)</span><span class="sxs-lookup"><span data-stu-id="9b3ca-223">Relational (Non-Join) Nodes</span></span>  
 <span data-ttu-id="9b3ca-224">Los siguientes tipos de expresión admiten nodos que no son de combinación:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-224">The following expression types support non-join nodes:</span></span>  
  
-   <span data-ttu-id="9b3ca-225">DbDistinctExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-225">DbDistinctExpression</span></span>  
  
-   <span data-ttu-id="9b3ca-226">DbFilterExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-226">DbFilterExpression</span></span>  
  
-   <span data-ttu-id="9b3ca-227">DbGroupByExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-227">DbGroupByExpression</span></span>  
  
-   <span data-ttu-id="9b3ca-228">DbLimitExpession</span><span class="sxs-lookup"><span data-stu-id="9b3ca-228">DbLimitExpession</span></span>  
  
-   <span data-ttu-id="9b3ca-229">DbProjectExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-229">DbProjectExpression</span></span>  
  
-   <span data-ttu-id="9b3ca-230">DbSkipExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-230">DbSkipExpression</span></span>  
  
-   <span data-ttu-id="9b3ca-231">DbSortExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-231">DbSortExpression</span></span>  
  
 <span data-ttu-id="9b3ca-232">La visita a estos nodos sigue este patrón:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-232">Visiting these nodes follows the following pattern:</span></span>  
  
1.  <span data-ttu-id="9b3ca-233">Visite la entrada relacional y obtenga la instrucción SqlSelectStatement resultante.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-233">Visit the relational input and get the resulting SqlSelectStatement.</span></span> <span data-ttu-id="9b3ca-234">La entrada a un nodo relacional puede ser:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-234">The input to a relational node could be one of the following:</span></span>  
  
    -   <span data-ttu-id="9b3ca-235">Un nodo relacional, incluida una extensión (una expresión DbScanExpression, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="9b3ca-235">A relational node, including an extent (a DbScanExpression, for example).</span></span> <span data-ttu-id="9b3ca-236">Al visitar este tipo de nodo, se devuelve una instrucción SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-236">Visiting such a node returns a SqlSelectStatement.</span></span>  
  
    -   <span data-ttu-id="9b3ca-237">Una expresión de operación set (UNION ALL, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="9b3ca-237">A set operation expression (UNION ALL, for example).</span></span> <span data-ttu-id="9b3ca-238">El resultado tiene que incluirse entre corchetes y colocarse en la cláusula FROM de una nueva instrucción SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-238">The result has to be wrapped in brackets and put in the FROM clause of a new SqlSelectStatement.</span></span>  
  
2.  <span data-ttu-id="9b3ca-239">Compruebe si el nodo actual se puede agregar a la instrucción SqlSelectStatement generada por la entrada.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-239">Check whether the current node can be added to the SqlSelectStatement produced by the input.</span></span> <span data-ttu-id="9b3ca-240">Esto se describe en la sección titulada Agrupar expresiones en instrucciones SQL.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-240">The section titled Grouping Expressions into SQL Statements describes this.</span></span> <span data-ttu-id="9b3ca-241">En caso contrario,</span><span class="sxs-lookup"><span data-stu-id="9b3ca-241">If not,</span></span>  
  
    -   <span data-ttu-id="9b3ca-242">Extraiga el objeto SqlSelectStatement actual.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-242">Pop the current SqlSelectStatement object.</span></span>  
  
    -   <span data-ttu-id="9b3ca-243">Cree un nuevo objeto SqlSelectStatement y agregue el objeto SqlSelectStatement extraído como la cláusula FROM del nuevo objeto SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-243">Create a new SqlSelectStatement object and add the popped SqlSelectStatement as the FROM of the new SqlSelectStatement object.</span></span>  
  
    -   <span data-ttu-id="9b3ca-244">Coloque el nuevo objeto en la parte superior de la pila.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-244">Put the new object on top of the stack.</span></span>  
  
3.  <span data-ttu-id="9b3ca-245">Redirija el enlace de expresión de entrada al símbolo correcto de la entrada.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-245">Redirect the input expression binding to the correct symbol from the input.</span></span> <span data-ttu-id="9b3ca-246">Esta información se conserva en el objeto SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-246">This information is maintained in the SqlSelectStatement object.</span></span>  
  
4.  <span data-ttu-id="9b3ca-247">Agregue un nuevo ámbito SymbolTable.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-247">Add a new SymbolTable scope.</span></span>  
  
5.  <span data-ttu-id="9b3ca-248">Visite la parte que no es de entrada de la expresión (por ejemplo, Projection y Predicate).</span><span class="sxs-lookup"><span data-stu-id="9b3ca-248">Visit the non-input part of the expression (for example, Projection and Predicate).</span></span>  
  
6.  <span data-ttu-id="9b3ca-249">Extraiga todos los objetos agregados a las pilas globales.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-249">Pop all the objects added to the global stacks.</span></span>  
  
 <span data-ttu-id="9b3ca-250">DbSkipExpression no tiene un equivalente directo en SQL.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-250">DbSkipExpression not have a direct equivalent in SQL.</span></span> <span data-ttu-id="9b3ca-251">Lógicamente, se traduce como:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-251">Logically, it is translated into:</span></span>  
  
```  
SELECT Y.x1, Y.x2, ..., Y.xn  
FROM (  
   SELECT X.x1, X.x2, ..., X.xn, row_number() OVER (ORDER BY sk1, sk2, ...) AS [row_number]   
   FROM input as X   
   ) as Y  
WHERE Y.[row_number] > count   
ORDER BY sk1, sk2, ...  
```  
  
### <a name="join-expressions"></a><span data-ttu-id="9b3ca-252">Expresiones de combinación</span><span class="sxs-lookup"><span data-stu-id="9b3ca-252">Join Expressions</span></span>  
 <span data-ttu-id="9b3ca-253">Las siguientes expresiones están consideradas como de combinación y se procesan de manera ordinaria utilizando el método VisitJoinExpression:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-253">The following are considered join expressions and they are processed in a common way, by the VisitJoinExpression method:</span></span>  
  
-   <span data-ttu-id="9b3ca-254">DbApplyExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-254">DbApplyExpression</span></span>  
  
-   <span data-ttu-id="9b3ca-255">DbJoinExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-255">DbJoinExpression</span></span>  
  
-   <span data-ttu-id="9b3ca-256">DbCrossJoinExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-256">DbCrossJoinExpression</span></span>  
  
 <span data-ttu-id="9b3ca-257">A continuación se enumeran los pasos que deben seguirse en la visita:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-257">The following are the visit steps:</span></span>  
  
 <span data-ttu-id="9b3ca-258">Primero, antes de visitar los elementos secundarios, es necesario llamar a IsParentAJoin para comprobar si el nodo de combinación es un elemento secundario de una combinación situada en un lateral izquierdo.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-258">First, before visiting the children, IsParentAJoin is invoked to check whether the join node is a child of a join along a left spine.</span></span> <span data-ttu-id="9b3ca-259">Si devuelve false, se inicia una nueva instrucción SqlSelectStatement.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-259">If it returns false, a new SqlSelectStatement is started.</span></span> <span data-ttu-id="9b3ca-260">En ese sentido, las combinaciones se visitan de forma diferente al resto de los nodos, ya que el elemento primario (el nodo de combinación) crea la instrucción SqlSelectStatement para que la usen posiblemente los elementos secundarios.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-260">In that sense, joins are visited differently from the rest of the nodes, as the parent (the join node) creates the SqlSelectStatement for the children to possibly use.</span></span>  
  
 <span data-ttu-id="9b3ca-261">En segundo lugar, procese las entradas de una en una.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-261">Second, process the inputs one at a time.</span></span> <span data-ttu-id="9b3ca-262">Para cada entrada:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-262">For each input:</span></span>  
  
1.  <span data-ttu-id="9b3ca-263">Visite la entrada.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-263">Visit the input.</span></span>  
  
2.  <span data-ttu-id="9b3ca-264">Posprocese el resultado de la visita a la entrada llamando a ProcessJoinInputResult, que se encarga de mantener la tabla de símbolos después de visitar un elemento secundario de una expresión de combinación y finalizar posiblemente la instrucción SqlSelectStatement generada por el elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-264">Post process the result of visiting the input by invoking ProcessJoinInputResult, which is responsible for maintaining the symbol table after visiting a child of a join expression and possibly finishing the SqlSelectStatement produced by the child.</span></span> <span data-ttu-id="9b3ca-265">El resultado del elemento secundario puede ser:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-265">The child's result could be one of the following:</span></span>  
  
    -   <span data-ttu-id="9b3ca-266">Un objeto SqlSelectStatement distinto del objeto al que se agregará el elemento principal.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-266">A SqlSelectStatement different from the one to which the parent will be added.</span></span> <span data-ttu-id="9b3ca-267">En este caso, puede que resulte necesario completarlo agregando columnas predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-267">In such case, it may need to be completed by adding default columns.</span></span> <span data-ttu-id="9b3ca-268">Si la entrada fue un objeto Join, tendrá que crear un nuevo símbolo de combinación.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-268">If the input was a Join, you need to create a new join symbol.</span></span> <span data-ttu-id="9b3ca-269">De lo contrario, cree un símbolo normal.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-269">Otherwise, create a normal symbol.</span></span>  
  
    -   <span data-ttu-id="9b3ca-270">Una extensión (una expresión DbScanExpression, por ejemplo), en cuyo caso simplemente se agrega a la lista de entradas de la instrucción SqlSelectStatement del elemento primario.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-270">An extent (a DbScanExpression, for example), in which case it is simply added to the list of inputs of the parent’s SqlSelectStatement.</span></span>  
  
    -   <span data-ttu-id="9b3ca-271">Un objeto que no es SqlSelectStatement, en cuyo caso se coloca entre corchetes.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-271">Not a SqlSelectStatement, in which case it is wrapped with brackets.</span></span>  
  
    -   <span data-ttu-id="9b3ca-272">El mismo objeto SqlSelectStatement al que se agrega el elemento primario.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-272">The same SqlSelectStatement to which the parent is added.</span></span> <span data-ttu-id="9b3ca-273">En este caso, los símbolos de la lista FromExtents deben sustituirse por un nuevo objeto JoinSymbol único que los represente a todos.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-273">In such case, the symbols in the FromExtents list need to be replaced with a single new JoinSymbol representing them all.</span></span>  
  
    -   <span data-ttu-id="9b3ca-274">En estos tres primeros casos, se llama a AddFromSymbol para agregar la cláusula AS y actualizar la tabla de símbolos.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-274">For the first three cases, AddFromSymbol is called to add the AS clause, and update the symbol table.</span></span>  
  
 <span data-ttu-id="9b3ca-275">En tercer lugar, se visita la condición de combinación (si existe).</span><span class="sxs-lookup"><span data-stu-id="9b3ca-275">Third, the join condition (if any) is visited.</span></span>  
  
### <a name="set-operations"></a><span data-ttu-id="9b3ca-276">Operaciones Set</span><span class="sxs-lookup"><span data-stu-id="9b3ca-276">Set Operations</span></span>  
 <span data-ttu-id="9b3ca-277">El método VisitSetOpExpression procesa las operaciones set DbUnionAllExpression, DbExceptExpression y DbIntersectExpression.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-277">The set operations DbUnionAllExpression, DbExceptExpression, and DbIntersectExpression are processed by the method VisitSetOpExpression.</span></span> <span data-ttu-id="9b3ca-278">Crea un objeto SqlBuilder del tipo</span><span class="sxs-lookup"><span data-stu-id="9b3ca-278">It creates a SqlBuilder of the shape</span></span>  
  
```xml  
<leftSqlSelectStatement> <setOp> <rightSqlSelectStatement>  
```  
  
 <span data-ttu-id="9b3ca-279">Donde \<leftSqlSelectStatement > y \<rightSqlSelectStatement > son instrucciones Sqlselectstatement obtenidas visitando cada una de las entradas, y \<setOp > es la operación correspondiente (UNION ALL, por ejemplo).</span><span class="sxs-lookup"><span data-stu-id="9b3ca-279">Where \<leftSqlSelectStatement> and \<rightSqlSelectStatement> are SqlSelectStatements obtained by visiting each of the inputs, and \<setOp> is the corresponding operation (UNION ALL for example).</span></span>  
  
### <a name="dbscanexpression"></a><span data-ttu-id="9b3ca-280">DbScanExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-280">DbScanExpression</span></span>  
 <span data-ttu-id="9b3ca-281">Si se visita en un contexto de combinación (como una entrada a una combinación que representa un elemento secundario izquierdo de otra combinación), la expresión DbScanExpression devuelve un objeto SqlBuilder con el SQL de destino del correspondiente destino, que puede ser una consulta de definición, una tabla o una vista.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-281">If visited in a join context (as an input to a join that is a left child of another join), DbScanExpression returns a SqlBuilder with the target SQL for the corresponding target, which is either a defining query, table, or a view.</span></span> <span data-ttu-id="9b3ca-282">De lo contrario, se crea una instrucción SqlSelectStatement con el campo FROM establecido para corresponderse con el destino correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-282">Otherwise, a new SqlSelectStatement is created with the FROM field set to correspond to the corresponding target.</span></span>  
  
### <a name="dbvariablereferenceexpression"></a><span data-ttu-id="9b3ca-283">DbVariableReferenceExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-283">DbVariableReferenceExpression</span></span>  
 <span data-ttu-id="9b3ca-284">La visita de una expresión DbVariableReferenceExpression devuelve el objeto Symbol correspondiente a esa expresión de referencia de variable en función de una búsqueda en la tabla de símbolos.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-284">The visit of a DbVariableReferenceExpression returns the Symbol corresponding to that variable reference expression based on a look up in the symbol table.</span></span>  
  
### <a name="dbpropertyexpression"></a><span data-ttu-id="9b3ca-285">DbPropertyExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-285">DbPropertyExpression</span></span>  
 <span data-ttu-id="9b3ca-286">La eliminación de la información de estructura jerárquica de los alias de combinación se identifica y procesa al visitar una expresión DbPropertyExpression.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-286">Join alias flattening is identified and processed when visiting a DbPropertyExpression.</span></span>  
  
 <span data-ttu-id="9b3ca-287">Primero se visita la propiedad Instance, lo que da como resultado un objeto Symbol, JoinSymbol o SymbolPair.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-287">The Instance property is first visited and the result is a Symbol, a JoinSymbol, or a SymbolPair.</span></span> <span data-ttu-id="9b3ca-288">A continuación se muestra cómo se tratan estos tres casos:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-288">Here is how these three cases are handled:</span></span>  
  
-   <span data-ttu-id="9b3ca-289">Si se devuelve un objeto JoinSymbol, su propiedad NameToExtent contiene un símbolo de la propiedad necesaria.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-289">If a JoinSymbol is returned, than its NameToExtent property contains a symbol for the needed property.</span></span> <span data-ttu-id="9b3ca-290">Si el símbolo de la combinación representa una combinación anidada, se devuelve un nuevo par Symbol con el símbolo de la combinación para realizar un seguimiento del símbolo que podría utilizarse como alias de la instancia y el símbolo que representa la propiedad real para una resolución posterior.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-290">If the join symbol represents a nested join, a new Symbol pair is returned with the join symbol to track the symbol that would be used as the instance alias, and the symbol representing the actual property for further resolving.</span></span>  
  
-   <span data-ttu-id="9b3ca-291">Si se devuelve un objeto SymbolPair y la parte Column es un símbolo de combinación, se devuelve de nuevo un símbolo de combinación, pero ahora la propiedad de columna se actualiza para señalar a la propiedad representada por la expresión de propiedad actual.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-291">If a SymbolPair is returned and the Column part is a join symbol, a join symbol is again returned, but now the column property is updated to point to the property represented by the current property expression.</span></span> <span data-ttu-id="9b3ca-292">De lo contrario, se devuelve un objeto SqlBuilder con el origen de SymbolPair como alias y el símbolo de la propiedad actual como columna.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-292">Otherwise a SqlBuilder is returned with the SymbolPair source as the alias, and the symbol for the current property as the column.</span></span>  
  
-   <span data-ttu-id="9b3ca-293">Si se devuelve un objeto Symbol, el método Visit devuelve un método SqlBuilder con esa instancia como alias y el nombre de propiedad como nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-293">If a Symbol is returned, the Visit method returns a SqlBuilder method with that instance as the alias, and the property name as column name.</span></span>  
  
### <a name="dbnewinstanceexpression"></a><span data-ttu-id="9b3ca-294">DbNewInstanceExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-294">DbNewInstanceExpression</span></span>  
 <span data-ttu-id="9b3ca-295">Cuando se utiliza como la propiedad Projection de DbProjectExpression, DbNewInstanceExpression genera una lista separada por comas de los argumentos para representar las columnas proyectadas.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-295">When used as the Projection property of DbProjectExpression, DbNewInstanceExpression produces a comma-separated list of the arguments to represent the projected columns.</span></span>  
  
 <span data-ttu-id="9b3ca-296">Cuando DbNewInstanceExpression tiene un tipo de valor devuelto de colección, y define una nueva colección de las expresiones proporcionadas como argumentos, los tres casos siguientes se tratan por separado:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-296">When DbNewInstanceExpression has a collection return type, and defines a new collection of the expressions provided as arguments, the following three cases are handled separately:</span></span>  
  
-   <span data-ttu-id="9b3ca-297">Si DbNewInstanceExpression tiene DbElementExpression como único argumento, se traduce como:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-297">If DbNewInstanceExpression has DbElementExpression as the only argument, it is translated as follows:</span></span>  
  
    ```  
    NewInstance(Element(X)) =>  SELECT TOP 1 …FROM X  
    ```  
  
 <span data-ttu-id="9b3ca-298">Si DbNewInstanceExpression no tiene ningún argumento (representa una tabla vacía), DbNewInstanceExpression se traduce como:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-298">If DbNewInstanceExpression has no arguments (represents an empty table), DbNewInstanceExpression is translated into:</span></span>  
  
```  
SELECT CAST(NULL AS <primitiveType>) as X  
FROM (SELECT 1) AS Y WHERE 1=0  
```  
  
 <span data-ttu-id="9b3ca-299">De lo contrario, DbNewInstanceExpression genera una escala union-all de los argumentos:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-299">Otherwise DbNewInstanceExpression builds a union-all ladder of the arguments:</span></span>  
  
```  
SELECT <visit-result-arg1> as X  
UNION ALL SELECT <visit-result-arg2> as X  
UNION ALL …  
UNION ALL SELECT <visit-result-argN> as X  
```  
  
### <a name="dbfunctionexpression"></a><span data-ttu-id="9b3ca-300">DbFunctionExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-300">DbFunctionExpression</span></span>  
 <span data-ttu-id="9b3ca-301">Las funciones canónicas e integradas se procesan de la misma manera: si necesitan un control especial (TRIM(cadena) como LTRIM(RTRIM(cadena), por ejemplo), se invoca al controlador adecuado.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-301">Canonical and built-in functions are processed the same way: if they need special handling (TRIM(string) to  LTRIM(RTRIM(string), for example), the appropriate handler is invoked.</span></span> <span data-ttu-id="9b3ca-302">De lo contrario, se traducen como FunctionName(arg1, arg2, ..., argn).</span><span class="sxs-lookup"><span data-stu-id="9b3ca-302">Otherwise they are translated to FunctionName(arg1, arg2, ..., argn).</span></span>  
  
 <span data-ttu-id="9b3ca-303">Se utilizan diccionarios para realizar un seguimiento de qué funciones necesitan un control especial y sus controladores adecuados.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-303">Dictionaries are used to keep track of which functions need special handling and their appropriate handlers.</span></span>  
  
 <span data-ttu-id="9b3ca-304">Las funciones definidas por el usuario se traducen como NamespaceName.FunctionName(arg1, arg2, ..., argn).</span><span class="sxs-lookup"><span data-stu-id="9b3ca-304">User-defined functions are tanslated to NamespaceName.FunctionName(arg1, arg2, ..., argn).</span></span>  
  
### <a name="dbelementexpression"></a><span data-ttu-id="9b3ca-305">DbElementExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-305">DbElementExpression</span></span>  
 <span data-ttu-id="9b3ca-306">El método que visita DbElementExpression solamente se invoca para visitar una expresión DbElementExpression cuando se usa para representar una subconsulta escalar.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-306">The method that visits DbElementExpression is only invoked for visiting a DbElementExpression when used to represent a scalar subquery.</span></span> <span data-ttu-id="9b3ca-307">Por consiguiente, DbElementExpression se traduce en una instrucción SqlSelectStatement completa y agrega corchetes alrededor de ella.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-307">Therefore, DbElementExpression translates into a complete SqlSelectStatement and adds brackets around it.</span></span>  
  
### <a name="dbquantifierexpression"></a><span data-ttu-id="9b3ca-308">DbQuantifierExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-308">DbQuantifierExpression</span></span>  
 <span data-ttu-id="9b3ca-309">En función del tipo de expresión (Any u All), la expresión DbQuantifierExpression se traduce como:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-309">Depending on the expression type (Any or All), DbQuantifierExpression is translated it as:</span></span>  
  
```  
Any(input, x) => Exists(Filter(input,x))  
All(input, x) => Not Exists(Filter(input, not(x))  
```  
  
### <a name="dbnotexpression"></a><span data-ttu-id="9b3ca-310">DbNotExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-310">DbNotExpression</span></span>  
 <span data-ttu-id="9b3ca-311">En algunos casos, es posible contraer la traducción de DbNotExpression con su expresión de entrada.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-311">In some cases it is possible to collapse the translation of DbNotExpression with its input expression.</span></span> <span data-ttu-id="9b3ca-312">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-312">For example:</span></span>  
  
```  
Not(IsNull(a)) =>  "a IS NOT NULL"  
Not(All(input, x) => Not (Not Exists(Filter(input, not(x))) => Exists(Filter(input, not(x))  
```  
  
 <span data-ttu-id="9b3ca-313">El motivo por el que se contrae por segunda vez es porque el proveedor introdujo ineficacias al traducir una expresión DbQuantifierExpression de tipo All.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-313">The reason the second collapse is performed is because inefficiencies were introduced by the provider when translating DbQuantifierExpression of type All.</span></span> <span data-ttu-id="9b3ca-314">Por consiguiente, Entity Framework no podría haber realizado la simplificación.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-314">Thus the Entity Framework could not have done the simplification.</span></span>  
  
### <a name="dbisemptyexpression"></a><span data-ttu-id="9b3ca-315">DbIsEmptyExpression</span><span class="sxs-lookup"><span data-stu-id="9b3ca-315">DbIsEmptyExpression</span></span>  
 <span data-ttu-id="9b3ca-316">DbIsEmptyExpression se traduce como:</span><span class="sxs-lookup"><span data-stu-id="9b3ca-316">DbIsEmptyExpression is translated as:</span></span>  
  
```  
IsEmpty(inut) = Not Exists(input)  
```  
  
## <a name="second-phase-of-sql-generation-generating-the-string-command"></a><span data-ttu-id="9b3ca-317">Segunda fase de la generación de SQL: Generar el comando String</span><span class="sxs-lookup"><span data-stu-id="9b3ca-317">Second Phase of SQL Generation: Generating the String Command</span></span>  
 <span data-ttu-id="9b3ca-318">Al generar un comando SQL string, el objeto SqlSelectStatement genera los alias reales de los símbolos, lo que resuelve el problema del cambio de nombre de la columna y del alias de extensión.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-318">When generating a string SQL command, the SqlSelectStatement produces actual aliases for the symbols, which addresses the issue of column name and extent alias renaming.</span></span>  
  
 <span data-ttu-id="9b3ca-319">El cambio de nombre del alias de extensión se produce al escribir el objeto SqlSelectStatement en una cadena.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-319">Extent alias renaming occurs while writing the SqlSelectStatement object into a string.</span></span> <span data-ttu-id="9b3ca-320">Primero, cree una lista de todos los alias utilizados por las extensiones exteriores.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-320">First create a list of all the aliases used by the outer extents.</span></span> <span data-ttu-id="9b3ca-321">El nombre de cada símbolo en la propiedad FromExtents (o en AllJoinExtents si no es null) se cambia si entra en colisión con alguna de las extensiones exteriores.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-321">Each symbol in the FromExtents (or AllJoinExtents if it is non-null), gets renamed if it collides with any of the outer extents.</span></span> <span data-ttu-id="9b3ca-322">Si se necesita un cambio de nombre, no estará en conflicto con ninguna de las extensiones recopiladas en AllExtentNames.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-322">If renaming is needed, it will not conflict with any of the extents collected in AllExtentNames.</span></span>  
  
 <span data-ttu-id="9b3ca-323">El cambio de nombre de una columna se produce cuando se escribe un objeto Symbol en una cadena.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-323">Column renaming occurs while writing a Symbol object to a string.</span></span> <span data-ttu-id="9b3ca-324">AddDefaultColumns en la primera fase ha determinado si debe cambiarse el nombre de un determinado símbolo de columna.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-324">AddDefaultColumns in the first phase has determined if a certain column symbol has to be renamed.</span></span> <span data-ttu-id="9b3ca-325">En la segunda fase, el cambio de nombre solamente se produce tras asegurarse de que el nombre generado no estará en conflicto con ninguno de los nombres utilizados en AllColumnNames</span><span class="sxs-lookup"><span data-stu-id="9b3ca-325">In the second phase only the rename occurs making sure that the name produced does not conflict with any name used in AllColumnNames</span></span>  
  
 <span data-ttu-id="9b3ca-326">Para generar nombres únicos tanto para los alias de extensión como para las columnas, utilice <nombre_existente>_n, donde n es el alias más pequeño que no se ha utilizado todavía.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-326">To produce unique names both for extent aliases and for columns, use <existing_name>_n where n is the smallest alias that has not been used yet.</span></span> <span data-ttu-id="9b3ca-327">La lista global de todos los alias aumenta la necesidad de realizar cambios de nombre en cascada.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-327">The global list of all aliases increases the need for cascading renames.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b3ca-328">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b3ca-328">See Also</span></span>  
 [<span data-ttu-id="9b3ca-329">Generación de SQL en el proveedor de ejemplo</span><span class="sxs-lookup"><span data-stu-id="9b3ca-329">SQL Generation in the Sample Provider</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)
