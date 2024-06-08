queue = []

# Enqueue
queue.append('A')
queue.append('B')
queue.append('C')
print("Queue: ", queue)

# Dequeue
element = queue.pop(0)
print("Dequeue: ", element)

# Peek
frontElement = queue[0]
print("Peek: ", frontElement)

# isEmpty
isEmpty = not bool(queue)
print("isEmpty: ", isEmpty)

# Size
print("Size: ", len(queue))
class Queue:
    def __init__(self):
        self.queue = []
    
  def enqueue(self, element):
        self.queue.append(element)
    
  def dequeue(self):
        if self.isEmpty():
            return "Queue is empty"
        return self.queue.pop(0)
    
   def peek(self):
        if self.isEmpty():
            return "Queue is empty"
        return self.queue[0]
    
   def isEmpty(self):
        return len(self.queue) == 0
    
   def size(self):
        return len(self.queue)

# Create a queue
myQueue = Queue()

myQueue.enqueue('A')
myQueue.enqueue('B')
myQueue.enqueue('C')
print("Queue: ", myQueue.queue)

print("Dequeue: ", myQueue.dequeue())

print("Peek: ", myQueue.peek())

print("isEmpty: ", myQueue.isEmpty())

print("Size: ", myQueue.size())
def hash_function(value):
    sum_of_chars = 0
    for char in value:
        sum_of_chars += ord(char)
return sum_of_chars % 10

print("'Bob' has hash code:",hash_function('Bob'))
my_hash_set = [None,'Jones',None,'Lisa',None,'Bob',None,'Siri','Pete',None]

def hash_function(value):
    sum_of_chars = 0
    for char in value:
        sum_of_chars += ord(char)

  return sum_of_chars % 10
    
def contains(name):
    index = hash_function(name)
    return my_hash_set[index] == name

print("'Pete' is in the Hash Set:",contains('Pete'))
class SimpleHashSet:
    def __init__(self, size=100):
        self.size = size
        self.buckets = [[] for _ in range(size)]  # A list of buckets, each is a list (to handle collisions)

   def hash_function(self, value):
        # Simple hash function: sum of character codes modulo the number of buckets
        return sum(ord(char) for char in value) % self.size

  def add(self, value):
        # Add a value if it's not already present
        index = self.hash_function(value)
        bucket = self.buckets[index]
        if value not in bucket:
            bucket.append(value)

 def contains(self, value):
        # Check if a value exists in the set
        index = self.hash_function(value)
        bucket = self.buckets[index]
        return value in bucket

  def remove(self, value):
        # Remove a value
        index = self.hash_function(value)
        bucket = self.buckets[index]
        if value in bucket:
            bucket.remove(value)

  def print_set(self):
        # Print all elements in the hash set
        print("Hash Set Contents:")
        for index, bucket in enumerate(self.buckets):
            print(f"Bucket {index}: {bucket}")

