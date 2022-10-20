# Learnable-Internship

const nthMostRare = (list, n) => {

    
           
        // Sort the list array
        list.sort();
       
        
        let lowestCount = n + 1, res = -1;
        let curr_count = 1;
           
        for (let i = 1; i < n; i++) {
            if (list[i] == list[i - 1])
                curr_count++;
            else {
                if (curr_count < lowestCount) {
                    lowestCount = curr_count;
                    res = list[i - 1];
                }
                   
                curr_count = 1;
            }
        }
       
        // If last element is least frequent
        if (curr_count < lowestCount)
        {
            lowestCount = curr_count;
            res = list[n - 1];
        }
       
        return res;
    }
 
        let list = [4, 3, 4, 2, 4, 2, 3, 2, 2, 3, 1];
        let n = list.length;
        console.log(nthMostRare(list, n));
