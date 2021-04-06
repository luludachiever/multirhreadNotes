# multirhreadNotes
class A {
private:
list<int> a;
 public:
  void read() {
      for (int i = 0; i < 100; ++i) {
           if (!a.emty()) {
                a.pop_front();
           }
      }
  }
  void write() {
      for (int i = 0; i < 100; ++i) {
           a.push_back(i);
       }
  }
};
 // this will have problem 
int main() {
  A obj;
  std::thread readT(&A::read, &obj);
  std::thread writeT(&A::write, &obj);
  readT.join();
  writeT.join();
   
}
