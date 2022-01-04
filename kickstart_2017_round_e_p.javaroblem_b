package com.company;

import java.io.*;
import java.util.HashMap;
import java.util.Map;

#kickstart 2017 round E problem B
#Copy & Paste

public class Main {
    static Map<String, Integer> vis = new HashMap<>();

    public static void main(String[] args) throws IOException {
        File file = new File("A-large-practice.in");
        BufferedReader br
                = new BufferedReader(new FileReader(file));
        int lines = Integer.parseInt(br.readLine());
        long startTime = System.nanoTime();
        for(int i=1;i<=lines;i++) {
            String s = br.readLine();
            int n = s.length();
            vis.clear();
            System.out.println("Case #"+i+": "+fun(0,"", s , n,  vis));
        }
        long endTime = System.nanoTime();
        System.out.println((endTime - startTime)/1e6);
    }

    private static int fun(int i, String cb, String s, int n, Map<String, Integer> vis) {
        if(i>n){
            return 10000;
        }
        if(i==n){
            return 0;
        }
        String key = i+cb;
        if(vis.getOrDefault(key, 10000)!=10000)
            return vis.get(key);
        int res = fun(i+1,cb, s, n, vis)+1;
        for(int x=0;x<=i;x++)
            for(int y=x+2;y<=i;y++){
                String ncb = s.substring(x,y);
                if(ncb.length()>1 && s.startsWith(ncb, i)){
                    int val = 2;
                    if(ncb.equals(cb)) val= 1;
                    res = Math.min(res, fun(i+ncb.length(), ncb, s, n, vis)+val);
                }
            }
        vis.put(key, res);
        return res;
    }
}
