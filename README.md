
# NSString.NSArray.NSDictionary
数组、字典、字符串相关常用语句整理

#import <Foundation/Foundation.h>

int main(int argc, const char * argv[]) {
    
//  字符串
    
//NSString
    
    //1.初始化
    
    NSString *string1 = [[NSString alloc] initWithFormat:@"i love you"];
    
    NSString *string2 = [[NSString alloc] initWithString:string1];
    
    NSString *string3 = [NSString stringWithFormat:@" never giveup"];
    
    NSString *string4 = [NSString stringWithString:string3];
    
    //2.字符串的长度
    
    NSLog(@"字符串的长度%lu", string1.length);
    
    //3.提取字符
    
    NSLog(@"提取字符%c", [string2 characterAtIndex:4]);
    
    //4.拼接字符串
    
    NSLog(@"拼接字符串%@", [string2 stringByAppendingString:string4]);
    
    NSLog(@"拼接字符串%@", [string4 stringByAppendingFormat:@" love"]);
    
    //5.替换字符串
    
    NSLog(@"替换字符串%@", [string4 stringByReplacingOccurrencesOfString:string4 withString:string2]);
    
    NSLog(@"替换字符串%@", [string2 stringByReplacingOccurrencesOfString:@"i" withString:@"I"]);
    
    //6.大小写字符串
    
    NSLog(@"全部大写%@", [string1 uppercaseString]);
    
    NSLog(@"全部小写%@", [string1 lowercaseString]);
    
    NSLog(@"首字母大写%@", [string1 capitalizedString]);
    
    //7.判断前后缀
    
    NSLog(@"原字符串%@", string1);
    
    NSLog(@"判断前缀%d", [string1 hasPrefix:@"i"]);
    
    NSLog(@"判断后缀%d", [string1 hasSuffix:@"you"]);
    
    //8.判断字符串是否相等
    
    NSLog(@"判断字符串是否相等%d", [string1 isEqualToString:string2]);
    
    NSLog(@"判断字符串是否相等%d", [string1 isEqualToString:string3]);
    
    //9.将字符串转换成基本数据类型
    
    NSString *stringNumber = @"2358";
    
    NSLog(@"将字符串转换成基本数据类型%ld", [stringNumber integerValue]);
    
    NSLog(@"将基本数据类型转换成字符串%@",  [NSString stringWithFormat:@"%ld", [stringNumber integerValue]]);
    
//  数组

//NSArray

    //1.初始化
    
    NSArray *array1 = [[NSArray alloc] initWithObjects:@"i", @"love", @"you", @"forever", nil];
    
    NSArray *array2 = [[NSArray alloc] initWithArray:array1];
    
    NSArray *array3 = [NSArray arrayWithObjects:@"never", @"give", @"up", nil];
    
    NSArray *array4 = [NSArray arrayWithArray:array3];

    //2.获取元素
    
   
    [array1 objectAtIndex:1];
   
    NSLog(@"获取元素%@", [array1 objectAtIndex:1]);
   
    [array1 firstObject];
   
    [array1 lastObject];

    //3.获取下标
    
    [array3 indexOfObject:@"give"];
    
    NSLog(@"获取下标%ld", [array3 indexOfObject:@"give"]);

    //4.判断是否含有给定对象

    [array2 containsObject:@"i"];

    NSLog(@"是否包含给定对象%d", [array2 containsObject:@"i"]);


//NSMutableArray

    NSMutableArray *muArray1 = [[NSMutableArray alloc] initWithArray:array4];

    NSMutableArray *muArray2 = [NSMutableArray arrayWithArray:array4];

    //5.增减元素
  
    [muArray1 addObject:@"forever"];

    NSLog(@"增加元素%@", muArray1);

    [muArray2 removeObject:@"give"];

    NSLog(@"移除元素%@", muArray2);

    //6.交换2个位子的元素

    [muArray1 exchangeObjectAtIndex:0 withObjectAtIndex:3];

    NSLog(@"交换2个位子的元素%@", muArray1);

    //7.替换元素

    [muArray1 replaceObjectAtIndex:0 withObject:@"i love you"];

    NSLog(@"替换元素%@", muArray1);

    //8.NSArray 与 NSString 相互转换方法

    NSArray *array = @[@"2", @"3", @"5", @"8"];

    // NSArray to NSString

    [array componentsJoinedByString:@"$_$"];

    NSLog(@"NSArray to NSString %@", [array componentsJoinedByString:@"$_$"]);

    // NSString to NSArray

    [array componentsJoinedByString:@"$_$"];

    NSLog(@"NSString to NSArray %@", [[array componentsJoinedByString:@"$_$"] componentsSeparatedByString:@"$_$"]);

    

    

// 字典

// NSDictionary

    //1.初始化

    NSDictionary *dictionary1 = [[NSDictionary alloc] initWithObjectsAndKeys:@"i", @"1", @"love", @"2", @"you", @"3", nil];

    NSDictionary *dictionary2 = [[NSDictionary alloc] initWithDictionary:dictionary1];

    NSDictionary *dictionary3 = [NSDictionary dictionaryWithObjectsAndKeys:@"never", @"1", @"give", @"2", @"up", @"3", nil];

    NSDictionary *dictionary4 = [NSDictionary dictionaryWithDictionary:dictionary3];

    //2.根据key取出value

    NSLog(@"%@", [dictionary2 objectForKey:@"2"]);

    //3.取出所有key和value

    NSLog(@"取出所有key和value%@", [dictionary4 allKeys]);

    NSLog(@"取出所有key和value%@", [dictionary4 allValues]);

    NSLog(@"取出所有key和value%@", dictionary2.allKeys);

    NSLog(@"取出所有key和value%@", dictionary2.allValues);

//NSMutableDictionary

    NSMutableDictionary *muDictionary1 = [NSMutableDictionary dictionaryWithDictionary:dictionary1];

    NSMutableDictionary *muDictionary2 = [[NSMutableDictionary alloc] initWithDictionary:dictionary3];

    //4.向字典内添加对象

    [muDictionary1 setObject:@"forever" forKey:@"4"];

    NSLog(@"向字典内添加对象 %@", muDictionary1);

    //5.修改key对应的value

    [muDictionary2 setObject:@"Never" forKey:@"1"];

    NSLog(@"修改key对应的value %@", muDictionary2);

    //6.移除元素

    [muDictionary1 removeObjectForKey:@"forever"];

    NSLog(@"移除元素%@", muDictionary1);

    

//for  in 循环
   
    NSMutableArray *forinarray1 = [NSMutableArray arrayWithArray:muArray1];
   
    NSMutableArray *forinarray2 = [[NSMutableArray alloc] initWithArray:forinarray1];
    
    for (NSString *str in forinarray1) {
        if ([str isEqualToString:@"never"]) {
            [forinarray2 replaceObjectAtIndex:[forinarray2 indexOfObject:str] withObject:@"Never"];
            //使用forin循环遍历时不能修改正在遍历的集合
            //当涉及到需要修改正在循环的集合时可以复制一份，循环复制出的一份，修改自己本身。
        }
    }
    for (NSString *str in forinarray2) {
        NSLog(@"替换%@", str);
    }
    
//排序
    
    NSArray *arrayOrder = @[@"12", @"4", @"78", @"0", @"18"];
    
    NSSortDescriptor *des = [[NSSortDescriptor alloc] initWithKey:nil ascending:1];
   
    NSArray *arrayDes = [NSArray arrayWithObject:des];
  
    NSLog(@"排序%@", [arrayOrder sortedArrayUsingDescriptors:arrayDes]);
    
  
    return 0;
}



