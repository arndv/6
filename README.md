# 6

Имате дадени следните твърдения: 



Губим възможността за произволен достъп. Няма начин, по който да индексираме k-тия елемент, без да минем през всички k-1 предходни. [Динамична имплементация]
Реализация на списък чрез масив, който автоматично увеличава размера си при нужда. [Статична имплементация]
Операциите добавяне и премахване от вътрешността  на списъка изискват пренареждане на елементите. [Статична имплементация]
Операциите добавяне и премахване от вътрешността  на списъка е бърза операция. [Динамична имплементация]
Търсенето на елементите в него е сравнително бърза операция. [Статична имплементация]
При често добавяне и премахване (особено при голям брой елементи) това може да доведе до ниска производителност. [Статична имплементация]
Можем да поддържаме паметта точно колкото ни трябва като сложността на добавяне си остава. [Динамична имплементация]
Елементите съдържат само конкретния обект. [Статична имплементация]
Всеки елемент съдържа променлива и указател, сочещ към следващия елемент. [Динамична имплементация]

Вашата задача е да сравните и откриете кои от тези твърдения се отнасят за статична реализация на списък и кои за динамична реализация на списък. 



Избройте поне четири операции (методи), които можете да прилагате върху списък.

Add(T item)
Remove(T item)
RemoveAt(int index)
Sort()
ToArray()



Дайте пример с C# код, за метод който да сортира  елементите от списъка List<int> list = new List<int>() { 12, 8, 10, 2, 9, 6, 1}; посредством алгоритъма за сортиране  чрез метода на мехурчето.


 public static void BubbleSortWithFor(List<int> list)
        {
            for (int j = 0; j <= list.Count - 2; j++)
            {
                for (int i = 0; i <= list.Count - 2; i++)
                {
                    if (list[i] > list[i + 1])
                    {
                        Swap(list, i, i + 1);
                    }
                }
            }
        }
private static void Swap(List<int> list, int index, int min)
        {
            int temp = list[index];
            list[index] = list[min];
            list[min] = temp;
        }
  
  
 
  
  Допишете метода Add(object item) който трябва да добави елемент в списъка. Обърнете внимание, че първоначалния размер на масива може да бъде прехвърлен!


public void Add(T element)
        {
            if(this.Length == this.Capacity)
            {
                this.Capacity *= 2;
                T[] temp = new T[this.Capacity];
                for (int i = 0; i < items.Length; i++)
                {
                    temp[i] = items[i];
                }
                temp[this.Length] = element;
                items = temp;
                this.Length++;
            }
            else
            {
                items[this.Length] = element;
                this.Length++;
            }
        }
                                                 
                                                 
![image](https://github.com/arndv/6/assets/125039034/be30428a-d123-46f9-a929-2a6147697f32)

                                                 
                                                 class CustomStack<T>
    {
        private class Node<T>
        {
            public T Value { get; set; }
            public Node<T> PrevNode { get; private set; }

            public Node(T value, Node<T> prev = null)
            {
                this.Value = value;
                this.PrevNode = prev;
            }
        }

        private Node<T> firstNode;
        public int Count { get; private set; }

     //    public void Push(T element)
        {
            this.firstNode = new Node<T>(element, this.firstNode);
            this.Count++;
        }
    //
            
}

Допишете метода Push(T element) който трябва да добави елемент в стека. Обърнете внимание на това каква имплементация на списъчната структура е използвана!



![image](https://github.com/arndv/6/assets/125039034/0ac78d8e-b16e-4ffd-abac-212a9a8245b3)

 
Посочете вярното твърдение за държавната списъчна структура в .NET - Queue<T>

Използва статичната реализация [ДА].
Абстрактната структура, която изпълнява условието "първият влязъл първи излиза". [ДА]
Използва динамична реализация [НЕ].
Абстрактна структура, която изпълнява  условието "последен влязъл – пръв излязъл" [НЕ]
Можем да добавяме елементи най-отгоре и да извличаме последния добавен елемент. [НЕ]
Добавените елементи се нареждат в края, а при извличане поредният елемент се взима от началото. [ДА]

 ![image](https://github.com/arndv/6/assets/125039034/602696a1-9971-4376-b345-1e95f6a4b5fb)

           
![image](https://github.com/arndv/6/assets/125039034/80b515d7-cc04-4309-bb07-f8b47c1f178f)

 В тази ситуация трябва да използваме списъчната структура от данни стек, защото поведението на елементите е от типа "първи влязъл - първи излиза". В случая, за да се намали времето за обработка на определен продукт, продуктите, които са доставени последни се обработват първи ни дава информацията, за структурата, която трябва да се използва в задачата.

Имате изброени методи за структура от данни, която има поведение от тип „първи влязъл, първи излязъл“. Свържете правилно всеки метод с неговото действие.
 Peek() → връща елемента от началото без да го изтрива, 
 Dequeue() → премахва и връща елемента от началото, 
 Enqueue → добавя елемент в края на опашката
 
Имате структура от данни, която има поведение от тип „последен влязъл, първи излиза“. Посочете правилно действието на всеки от методите:
 Push() → добавя елемент най-горе в стека, Pop() → премахва най-горният елемент в стека, Peek() → връща най-горният елемент в стека, без да го премахва 
 
![image](https://github.com/arndv/6/assets/125039034/351795f9-e706-417e-8b9b-e46f270007aa)

![image](https://github.com/arndv/6/assets/125039034/9723c087-1e91-45e2-b327-dcf5294b1013)

 ![image](https://github.com/arndv/6/assets/125039034/c198e220-4e1f-4fad-9855-25f4ba3bb65a)

 
 Избройте три операции (методи), които можете да прилагате върху опашка.

Enqueue (T item)
Dequeue ()
Peek ()
 
 
Имате даден следния код:

List<int> list = Console.ReadLine()
                .Split()
                .Select(int.Parse)
                .ToList();

            int currVal = list[0];
            int currCount = 1;
            int maxCount = 1;
            int maxValue = currVal;

            for (int i = 1; i < list.Count; i++)
            {
                if(currVal == list[i])
                {
                    currCount++;
                    if(currCount > maxCount)
                    {
                        maxCount = currCount;
                        maxValue = currVal;
                    }
                }
                else
                {
                    currCount = 1;
                    currVal = list[i];
                }
            }

            Console.WriteLine($"{maxValue} -> {maxCount}");

Свържете към намирането на коя от следните подредици съответства: [най‑дълга подредица от равни числа]
 
 
++++++++++++++++++
 
 Даден е следния програмен фрагмент:

class CustomList
    {
        private class Node
        {
            private object element;
            private Node next;
            public Node(object element, Node prevNode)
            {
                this.Element = element;
                prevNode.Next = this;
            }
            public Node(object element)
            {
                this.Element = element;
            }
            public object Element
            {
                get { return this.element; }
                set { this.element = value; }
            }
            public Node Next
            {
                get { return this.next; }
                set { this.next = value; }
            }
        }
        //полета
        //глава(начало) на списъка
        private Node head;
        //опашка(край) на списъка
        private Node tail;
        //броят на елементите в свързания списък
        private int count;
        public int Count
        {
            get { return this.count; }
            private set { this.count = value; }
        }
        public void Add(object element)
        {
           
        }

Допишете метода Add(object element) който трябва да добави елемент в списъка. Обърнете внимание на това каква имплементация на списъчната структура е използвана!



Забележка
public void Add(object element)
        {
            //ако броя на елементите ни е 0, т.е. ако няма елементи в списъка 
            if(count == 0)
            {
                //създаваме си един нов нод с елемента, който ни се подава
                Node newNode = new Node(element);
                //в такъв случай и началото и края ще са равни на този нов нод
                head = newNode;
                tail = newNode;
                //и броя на елементите ни се увеличава
                count++;
            }
            //в противен случай, ако вече имаме елементи в нашия списък
            else
            {
                //вече ще ползваме конструктора на класа Node на който подаваме елемента и опашката(предишния нод), или 
                //последния елемент в нашия списък
                Node newNode = new Node(element, tail);
                //казваме на последния елемент, че вече ще бъде равен на този нов нод
                tail = newNode;
                //и увеличаваме броя на елементите в нашия списък
                count++;
            }
        }
 
 ++++++++++++++++++++++++++++++++++

 Разработвате ново приложение за оптимизиране на процесите в работата на призводствено предприятие. Трябва да приложите структура от данни, която да работи като „буфер“ срещу надхвърляне на капацитета. Когато сме в рамките на призводствения капацитет, артикулите в буфера трябва да се обработят в реда, в който се добавят. Обяснете коя структура от данни трябва да използвате защо бихте използвали точно нея, за да приложите такъв буфер?

Забележка
В опашката, артикулите се обработват в реда, в който са добавени. В частност, артикулите се добавят в края на опашката и се премахват от началото. Това е общоизвестно като first-in, first-out (FIFO) обработване.
 
 
 ////
Разработвате приложение, което използва структурата от данни Stack<T>. Пишете следния код:

       Stack<int> processStack = new Stack<int>();

       processStack.Push(50);

       processStack.Push(45);

       processStack.Pop();

       processStack.Push(11);

       processStack.Pop();
  
       processStack.Push(7);

Какво ще бъде съдържанието на стека (stack), от горе на долу, след като се изпълнят изразите (инструкциите)?
Правилният отговор е: 7, 50
 
 ![image](https://github.com/arndv/6/assets/125039034/c05a34f8-e59c-42d4-ba79-16063ae1c818)

 
 
 Имате даден следния програмен фрагмент:
 ![image](https://github.com/arndv/6/assets/125039034/838f754d-37f8-4baa-aaf0-e271b4966f07)

 Този фрагмент е част от имплементацията на линейната структура от данни стек - премахване на елемент от стек. В кода има грешка! Вашата задача е да откриете грешката, да обясните каква е тя и по какъв начин ще я поправите!

Забележка
Грешката в кода е, че методът Pop(int index) получава цяло число, което вътре в метода се използва за намиране на елемента в масива и премахването на този елемент. По дефиниция линейната структура стек не работи така. Правилото за работа със стек е "първи влиза - първи излиза". Нямаме право да достъпваме елементите по индекс, освен само и единствено за четене. Когато правим имплементацията за премахване на елемент от стек винаги премахваме последния елемент - в случая трябва да използваме броя на елементите (Count) на мястото на параметъра Index, за да премахнем последния елемент от масива в класа. И самия метод Pop() не трябва да приема параметър.
 
 
 ![image](https://github.com/arndv/6/assets/125039034/cd291b2c-29c0-424f-bcd9-f85d50dba75f)

 public static void SelectionSort(List<int> list)
        {
            for (int index = 0; index < list.Count; index++)
            {
                int min = index;
                for (int current = index + 1; current < list.Count; current++)
                {
                    if(list[current] < list[min])
                    {
                        min = current;
                    }
                }

                Swap(list, index, min);
            }
            
        }

private static void Swap(List<int> list, int index, int min)

        {

            int temp = list[index];

            list[index] = list[min];

            list[min] = temp;

        }
 
 
 Имате даден следния код:

List<int> list = Console.ReadLine()
                .Split()
                .Select(int.Parse)
                .ToList();
            int currValue = list[0];
            int maxValue = currValue;
            int currCount = 1;
            int maxCount = 1;
            int counter = 1;
            for (int i = 1; i < list.Count; i++)
            {
                if (currValue - counter == list[i])
                {
                    currCount++;
                    counter++;
                    if (currCount > maxCount)
                    {
                        maxCount = currCount;
                        maxValue = currValue;
                    }

                }
                else
                {
                    currCount = 1;
                    currValue = list[i];
                    counter = 1;
                }

            }
            Console.WriteLine();
            Console.WriteLine(maxCount);

Свържете към намирането на коя от следните подредици съответства: [най‑дълга подредица от намаляващи числа]
 
 
 Даден е следния програмен фрагмент:

class CustomStack<T>
    {
        public const int INITIAL_CAPACITY = 16;

        private T[] items;
        public int Count { get; set; }

        public CustomStack(int initialCapacity = INITIAL_CAPACITY)
        {
            this.items = new T[initialCapacity];
        }

       //  public void Push(T element)
        {
            if (this.Count == this.items.Length)
            {
                //this.Grow();
                T[] temp = new T[this.items.Length * 2];
                for (int i = 0; i < this.Count; i++)
                {
                    temp[i] = items[i];
                }

                this.items = temp;
            }

            this.items[this.Count] = element;
            this.Count++;

}     

Допишете метода Push(T element) който трябва да добави елемент в стека. Обърнете внимание на това каква имплементация на списъчната структура е използвана!




![image](https://github.com/arndv/6/assets/125039034/b6c49744-9b21-4354-b4f7-b48e87cbbbab)

 Каква реализация на списъчна структура от данни представлява този код? Обобщете отговора си и напишете кратко обяснение, защо?
Динамична имплементация на стек. Защото в класа е деклариран друг клас, наречен Node(възел). Този клас ни служи като елемент (обект), който да пази стойността на елемента, който добавяме в стека(пропъртито Value) и също така съдържа и елемент отново от тип Node (PrevNode), който ще служи като указател към следващия постъпил елемент в стека. В този случай винаги имаме достъп до първия нод (възел) в стека, защото правилото при стека е първи влиза - първи излиза. По този начин реализираме свързан стек или използваме динамична имплементация, за да създадем наша собствена списъчна структура от данни - стек.


![image](https://github.com/arndv/6/assets/125039034/3f7f6cb0-3672-4a9f-997a-86490060501d)

                                               
                                               Правилният отговор е:
Имате даден следния код:

List<int> list = Console.ReadLine()
                .Split()
                .Select(int.Parse)
                .ToList();
            int currValue = list[0];
            int maxValue = currValue;
            int currCount = 1;
            int maxCount = 1;
            int counter = 1;
            for (int i = 1; i < list.Count; i++)
            {
                if(currValue + counter == list[i])
                {
                    currCount++;
                    counter++;
                    if(currCount > maxCount)
                    {
                        maxCount = currCount;
                        maxValue = currValue;
                    }
                    
                }
                else
                {
                    currCount = 1;
                    currValue = list[i];
                    counter = 1;
                }

            }
            Console.WriteLine();
            Console.WriteLine(maxCount);

Свържете към намирането на коя от следните подредици съответства: [най‑дълга подредица от нарастващи числа]
 
 
 
Имате имплементация на свързана опашка. При така написания код, посочете верния изход в конзолата и броят на елементите в опашката.

var queue = new LinkedQueue<int>();

                queue.Enqueue(112);

                queue.Enqueue(911);

                queue.Enqueue(166);

                queue.Enqueue(160);

                queue.Enqueue(150);

                queue.Dequeue();

                Console.WriteLine(string.Join(" ", queue));

                Console.WriteLine("Count = {0}", queue.Count);
.
Правилният отговор е: 911, 166, 160, 150, Count = 4










