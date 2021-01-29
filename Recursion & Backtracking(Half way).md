Question | Topic/Hints | Difficulty
| :--- | ---: | :---:
N Queens
Sudoku Solver
Permutaions I|Must Do|Basic
Permutaions II
Combination Sum I
Combination Sum II
Combination Sum III
Subset I
Subset II
```java
class Solution {
    public void swap(int[] arr, int a, int b){
        int temp=arr[a];
        arr[a]=arr[b];
        arr[b]=temp;
    }
    public void recur(HashMap<Integer, Integer> map, ArrayList<Integer> mini_res, List<List<Integer>> res, int actual_size){
        
        //stopping condition
        System.out.println(mini_res.size() +"  "+actual_size);
        for(Integer i: mini_res) System.out.print("  My list "+i);
        System.out.println();
        if(mini_res.size()==actual_size){
            System.out.println("i update");
            res.add(mini_res);
            return;
        }
        //backtracking formulae
        //1. traversing through the keys of the hashmap as choices at current stage
        //2. for every choice add the choice in mini result list
        //3. decrement its frequency
        //4. call the recur function to go to the next stage
        //5. after returning from the next stage 
        //6. increment the frequency or restore in map , remove the choice from mini result
        
        for(Map.Entry<Integer, Integer> entry : map.entrySet()){
            if(entry.getValue()!=0){
                mini_res.add(entry.getKey());
                map.put(entry.getKey(), entry.getValue()-1);
                
                recur(map, mini_res, res, actual_size);
                
                mini_res.remove(mini_res.size()-1);//removing the last element by passing index
                map.put(entry.getKey(), entry.getValue()+1);
            }
        }
        
    }
    public List<List<Integer>> permuteUnique(int[] nums) {
        List<List<Integer>> res=new ArrayList<>();
        
        HashMap<Integer, Integer> map=new HashMap<>();
        ArrayList<Integer> mini_res=new ArrayList<>();
        for(int n:nums){
            if(!map.containsKey(n)) map.put(n, 0);
            map.put(n, map.get(n)+1);
        }
        /*for(Map.Entry<Integer, Integer> entry : map.entrySet()){
            System.out.println(entry.getKey()+"   "+entry.getValue());
        }*/
        int n = nums.length;
        
        recur(map, mini_res, res, n);
        for(List<Integer> i: res){
            for(Integer j: i){
                System.out.print(j+" p ");
            }
            System.out.println();
        }
        return res;
    }
}
```
