# RecommendationSystem
Hệ thống gợi ý phim
-------------------
THÔNG TIN CHUNG
-------------------

1. Bài toán được viết trên Google Colab.
		Colaboratory hay còn gọi là Google Colab, là một sản phẩm từ Google Research, nó cho phép chạy các dòng code python thông qua trình duyệt, 
	đặc biệt phù hợp với Data analysis, machine learning và giáo dục. Colab không cần yêu cầu cài đặt hay cấu hình máy tính, mọi thứ có thể chạy thông qua trình duyệt, 
	bạn có thể sử dụng tài nguyên máy tính từ CPU tốc độ cao và cả GPUs và cả TPUs đều được cung cấp cho bạn.

		Colab cung cấp nhiều loại GPU, thường là Nvidia K80s, T4s, P4s and P100s, tuy nhiên người dùng không thể chọn loại GPU trong Colab, 
	GPU trong Colab thay đổi theo thời gian. Vì là dịch vụ miễn phí, nên Colab sẽ có những thứ tự ưu tiên trong việc sử dụng tài nguyên hệ thống, 
	cũng như giới hạn thời gian sử dụng, thời gian sử dụng tối đa lên tới 12 giờ.

	Cách truy nhập: đăng nhập Google--> chọn Drive--> mục mới--> kết nối ứng dụng khác--> chọn Colaboratory.


---------------------
TỔNG QUAN VỀ DỮ LIỆU & TẬP TIN
---------------------

# Đường link tải file dữ liệu: 
	http://files.grouplens.org/datasets/movielens/ml-latest-small.zip
# Thư mục Tệp trong Tập dữ liệu: 
	ml-latest-small/
	ml-latest-small/links.csv
	ml-latest-small/tags.csv
	ml-latest-small/ratings.csv
 	ml-latest-small/README.txt
	ml-latest-small/movies.csv
# tệp được bao gồm trong tập dữ liệu. 
	ml-latest-small/ratings.csv
	ml-latest-small/movies.csv
# nội dung: chứa tất cả các thông tin, trường dữ liệu về người dùng, tỉ lệ rating(đánh giá) của phim, thời gian,...
#

#
# Quy ước Đặt tên Tệp: đặt tên đúng với vai trò của tên tệp 
	ratings_df = pd.read_csv(zipfile.open('ml-latest-small/ratings.csv'))
	movies_df = pd.read_csv(zipfile.open('ml-latest-small/movies.csv'))

-----------------------------------------
--------------------------
# Thư viện áp dụng:
# Lệnh tải scikit surprise:  ---- !pip install surprise-----:để xây dựng và phân tích các hệ thống đề xuất xử lý dữ liệu xếp hạng rõ ràng, 
				          cho phép lập trình viên có thể dùng dữ liệu được cài sẵn, 
				          Cung cấp các thuật toán dự đoán sẵn sàng sử dụng khác nhau như  baseline algorithms, neighborhood methods,
				          dựa trên thừa số hóa ma trận ( SVD , PMF , SVD ++ , NMF ) và nhiều thuật toán khác



