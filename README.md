# North_west_corner
Python code for North West Corner rule

def north_west_corner (supply, demand):

    supply_copy = supply[:]
    
    demand_copy = demand[:]
    
    i = 0
    
    j = 0
    
    bfs = []
    
    while len(bfs) < len (supply) + len(demand) - 1:
    
        s = supply_copy[i]
        
        d = demand_copy[j]
        
        v = min(s,d)
        
        supply_copy[i] -= v
        
        demand_copy[j] -= v
        
        bfs.append(((i,j),v))
        
        if supply_copy[i] == 0 and i<len (supply) -1:
        
            i += 1
            
        elif demand_copy[j] == 0 and j<len(demand) -1:
        
            j += 1
            
    return bfs
    
supply = [30,70,50]

demand = [40,30,40,40]

bfs = north_west_corner (supply, demand)

print("The output is:- \n", bfs)

