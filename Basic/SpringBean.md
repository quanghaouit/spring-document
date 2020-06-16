### POJO (plain old java object)
- Là một object không có bất cứ ràng buộc nào cả ngoại trừ các ràng buộc mặc định của java. Ví dụ như các spec của java.
- POJO không kế thừa class nào cả ngoại trừ class object mặc định trong gói java lang của java và override lại các phương thức của nó như toString, hashcode, ... và nên có hàm khởi tạo không tham số
- POJO cũng không nên kế thừa interface nào cả.
- POJO cũng không nên có các anotation trong các khai báo của nó.

### Java beans
- Là các class có hàm khởi tạo không tham số được đặt là public.
- Có các hàm getter, setter để truy cập vào các thuộc tính private của nó.
- Thừa kế interface serializable để có thể truyền qua mạng theo cơ chế line mode hoặc đọc file và ghi file 

### Spring beans
- Bất cứ object nào được khởi tạo, cấu hình và quản lý bởi spring container thì đều được hiểu là spring beans. Như là model, service, repository.
- Spring beans có thể được khai báo, định nghĩa trong các file configuration, anotation hoặc các referrence. 
- Spring beans không nhất thiết phải là java beans -> không cần serialization hoặc hàm khởi tạo không tham số.