# Swift_Graphs

class vertix: Hashable{
    
    static func == (lhs: vertix, rhs: vertix) -> Bool {
         return lhs.value == rhs.value
    }
    
    var value: Int?
    var edges = [[Int:Int]]()
    init(value: Int?, edges: [[Int:Int]]) {
        self.value = value
        self.edges = edges
    }
    var hashValue: Int {
        return value.hashValue
    }
   
}

class Graph{
    var graph: Array<vertix>?
    init(graph: Array<vertix>?) {
        self.graph = graph
    }
    func addVertix( v: vertix){
        graph!.append(v)
    }
    func addEdges(from: vertix, to: Int, cost: Int){
        from.edges.append([to:cost])
        let edge = from.edges
        from.edges = edge
    }

}





let G = Graph(graph: [])

let n = vertix(value: 2, edges: [])
let c = vertix(value: 4, edges: [])

G.addVertix( v: n)
G.addVertix( v: c)

G.addEdges(from: n, to: c.value!, cost: 100)

for v in G.graph!{
    for e in v.edges{
        print(v.value!, e)
    }
}
