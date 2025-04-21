Đặc điểm quạn trọng của Cassandra : 
 - Cassandra hoạt động trên một hợp các máy chủ gọi là "node". Mỗi node chưa một phần dữ liệu và có thể đóng vai trò như một node ghi hoặc node đọc. 
	Node có thể thêm và hoặc loại bỏ từ cụm một cách dễ dàng để mở rộng hoặc thu nhỏ khả năng lưu trữ và xử lý dữ liệu
 - sao lưu dữ liệu. Cassandra sử dụng mô hình sao lưu dữ liệu đa phân vùng để đảm bảo tính khả dụng và độ tin cậy.
	Mỗi phân vùng được sao lưu trên nhiều node trong cụm. Số lượng node sao lưu cho mỗi phân vùng được xác định bở Replication Factor, mà bạn có thể cấu hình tuỳ chỉnh
 - Từ khoá phân vùng (Partition Key): để xác định cách dữ liệu được phân thành các vùng, Cassandra sử dụng một hoặc nhiều cột gọi là Partition Key. Dữ liệu
	có cùng Partition Key sẽ được lưu trữ trên cùng một phân vùng và có thể được truy cập nhanh chóng bằng cách sử dụng Partition key này.
 - Consistency Level: Cassandra cho phép cấu hình mức độ nhất quán của dữ liệu thông qua Consistency Level. Bằng cách xác định Consistency Level, 
	bạn có thể kiểm soát cách đọc và ghi dữ liệu đối với các nút trong cụm
 - Tính khả dụng và khả năng chịu lỗi: Cassandra được thiết kế để chịu lỗi và sự cố mà không ảnh hưởng đến tính khả dụng. Với dữ liệu được sao lưu trên nhiều node và phân vùng,
	thậm chí khi một số node hoặc phân vùng gặp sự cố, hệ thống vẫn tiếp tục hoạt động
 - Mở rộng linh hoạt: Bạn có thể mở rộng Cassandra bằng cách thêm node vào cụm mà không ảnh hưởng đến tính khả dụng. Điều này làm cho Cassandra phù hợp cho các ứng dụng có yêu cầu mở rộng lớn
 
Các khái niệm quan trọng:
 - Cluster: là một tập hợp hoắc nhóm các máy chủ(node) làm việc cùng nhau để lưu trữ và quản lý dữ liệu. Cụm này hoạt động như một hệ thống quản lý cơ sở dữ liệu phân tán, nơi bạn có thể
	lưu trữ và truy xuất dữ liệu trên nhiều node máy chủ khác nhau.
	+ Cluster cho phép thêm node vào hệ thống một cách dễ dàng để mở rộng lưu trữ và xử lý dữ liệu khi cần thiết
	+ Dữ liệu không được lưu trữ trên một máy chủ duy nhất. Thay vào đó, nó được chia thành các phân vùng(partitions) và lưu trữ trên nhiều node máy chủ khác nhau trong Cluster
	+ Cluster là nơi quyết định về cấu trúc, cấu hình, và quyền truy cập dữ liệu. Bạn có thể cấu hình các keyspace và bảng trong cụm để tổ chức và quản lý dữ liệu
	+ 
	
 - Node : là một máy chủ hoạt động trong Cluster. Node là thành phần cơ bản của Cluster và đón vai trò quan trọng trong việc lưu trữ
	truy xuất và quản lý dữ liệu
	+ Mỗi node Cassandra chưa một phần của dữ liệu trong hệ thống. Dữ liệu được phân chia thành các vùng(partitions), và mỗi node lưu trữ một số lượng phân vùng cụ thể. 
	+ Phân vùng là một phần nhỏ của dữ liệu được lưu trữ và quản lý bởi 1 node cụ thể. Dữ liệu trong mỗi phân vùng được xác định bởi PRIMARY KEY của nó
	+ Mỗi node hoạt động đọc lập với các node khác trong Cluster. Điều này có nghĩa rằng một node có thể được thực hiện các truy vấn đọc và ghi dữ liệu mà không cần phụ thuộc và các node khác
	+ Dữ liệu được phân vùng hoá để phân phối dữ liệu trên các node một cách hiệu quả. Mỗi phân vùng được quản lý bởi một node cụ thể
	+ Dữ liệu trên mỗi node thường có 1 hoặc nhiều bản sao để đảm bảo tính khả dụng và độ tin cậy. Một số bản sao của dữ liệu được lưu trữ trên các node khác trong cụm
	+ Khi 1 node gặp sự cố hoặc không thể truy cập, dữ liệu vẫn có thể được truy xuất từ các bản sao lưu trữ trên các node khác
	
	
 - Keyspaces: Keyspaces tương đương với cơ sở dữ liệu tỏng hệ thống quản lý csdl SQL. Nó là không gian chứa dữ liệu và bạn có thể tạo nhiêu keyspaces cho các ứng dụng khác nhau.
	Mỗi keyspaces chứa các bảng và có cài đặt riêng biệt cho sao lưu dữ liệu.
 - Table: trong Cassandra, mỗi keyspaces chưa một hoặc nhiều table, Một table là nơi bạn lưu trữ dữ liệu. Mỗi table có một tên duy nhất và bao gồm các cột. Các cột được	
	sắp xếp thành các hàng và mỗi hàng có một giá trị duy nhất được gọi là PRIMARY Key
 - PRIMARY KEY: PRIMARY KEY trong Cassandra là cột hoặc một tập hợp các cột được sử dụng để xác định duy nhất một hàng trong bảng. PRIMARY KEY bao gồm 2 phần : 
	+ Partition Key : được sử dụng để phân vùng dữ liệu
	+ Clustering: được sử dụng để sắp xếp dữ liệu trong phân vùng
 - Partition Key: là một hoặc nhiều cột trong PRIMARY KEY được sử dụng để phân chia dữ liệu thànhc ác vùng. Mỗi phân vùng có thể chứ nhiều hàng dữ liệu.
	Dữ liệu trong mỗi phân vùng được sao lưu trên các nút khác nhau trong cụm Cassandra
 - Clustering Columns: Clustering Columns là các cột trong PRIMARY Key được sử dụng để sắp xếp dữ liệu trong một phân vùng. Dữ liệu trong mỗi phân vùng được sắp xếp dựa trên giá trị của Clustering columns
 - Replication Factor: Replication Factor xác định số lượng sao lưu của dữ liệu trên các node trong cụm Cassandra. Điều này đảm bảo tính khả dụng và độ tin cậy của dữ liệu.
	Thay đổi Replication Factor có thể được thực hiện tại mỗi keyspace
 - Consistency Level: Consistency Level xác định mức độ nhất quán của dữ liệu trong quá trình đọc và ghi. Bằng cách thiết lập Consistency Level, bạn có thể kiểm soát cách dữ liệu được đọc và ghi
 - TTL(Time To Live): là một tuỳ chọn bạn có thể ấp dụng trong các cột Casandra để xác định thời gian tồn tại của dữ liệu. Sau khi TTL hết, dữ liệu sẽ bị xoá tự động
 - Compaction: là quá trình tối ưu hoá dữ liệu bằng cách loại bỏ dữ liệu đã xoá và sắp xếp lại dữ liệu cơ sở để giảm dung lượng lưu trữ và cải thiện hiệu suất.
 - CQL(Cassandra Query Language): CQL là ngôn ngữ truy cấn Casandra tương tự SQL. Bạn sử dụng CQL để thực hiện truy bấn và tương tác với dữ liệu tỏng Cassandra
 
Câu lệnh CQL:
 - CREATE KEYSPACE test_keyspace WITH replication = {'class': 'SimpleStrategy','replication_factor':'1'} AND durable_writes = 'true' : Tạo keyspace
 - DESCRIBE KEYSPACES : danh sách keyspaces
 - DROP KEYSPACE test_keyspace : xoá keyspace có tên là test_keyspace
 
 - CREATE TABLE products(id int PRIMARY KEY, nam text): tạo Tables
 - DESCRIBE TABLES : danh sách tables
 - DROP TABLE products : xoá bảng có tên là products
 - DESCRIBE TABLE products: mô tả chi tiết về thông tin của bảng products
 
 - CONSISTENCY QUORUM :
 - CONSISTENCY ONE :
 - UPDATE products USING TTL 60 SET name =  'product 7' WHERE id =5 : Thay đổi giá trị name của record có id =5. Hết 60 giây giá trị name của record này sẽ thành null 
 - ALTER TABLE products add category set<text>: thêm cột category có kiểu dữ liệu là set<text> cho bảng products
 - UPDATE products SET category = {'category 1'} WHERE id =5
 - UPDATE products SET category = category + {'category 2'} WHERE id =5
 - SELECT * FROM  products  WHERE name = 'product 1' ALLOW FILTERING : thêm ALLOW FILTERING vào cuối câu truy vấn sẽ cho phép where theo điều kiện không phải là primary key
 - CREATE TABLE product_view (product_id int PRIMARY KEY, view_count COUNTER); 
