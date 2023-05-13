# Nodes
- node là một máy chạy trên pods. 
- node là một physical machine or virtual machine
- một Node phải có những yêu cầu: 
    - Mỗi node phải có một kubelet  running
    - Một nodes trong k8s là một máy chạy các pods
    - kube-proxy running
    - node can process like supervisor and restart process
### PODS

-  gồm một hoặc nhiều container được lên lịch cùng nhau trên cùng một node
-   ### PODS and containers
    -  Một container nhẹ, môi trường thực thi cô lập đóng gói mã và các phần phụ thuộc của nó lại với nhau
    -   Container thiết kế để di động và chạy trên mọi cơ sở hạ tầng nào hỗ trợ Docker
-   ### Pods and Kubenetes control plane

    -  Mặt phẳng điều khiển kubenetes <Kubenetes control plane> là một tập hợp các thành phần quản lý kubernetes cluster <cụm kubernetes>. 
    -  Mặt phẳng điều khiển bao gồm kube-apiserver, kube-scheduler, kube-controller-manager 
-   ### Pods and networking

    -   Pods có địa chỉ riêng và có thể giao tiếp với nhau qua mạng. Pods cũng có thể được tiếp xúc bên ngoài thông qua dịch vụ
-   ### Pods and storage

    -   Pods có thể sử dụng nhiều tùy chọn lưu trữ, bao gồm lưu trữ cục bộ, lưu trữ liên tục (presistent volume), lưu trữ mạng 
-   ### Pods and security

    -  Pods có thể được bảo mật dùng với nhiều cách cách. bao gồm chính sách mạng, chính sách bảo mật pods (podSecurityPolicies), and secrets (bí mật)
-   ### Pods and scalability

    -   Pods có thể mở rộng và có thể được mở rộng lên hoặc thu nhỏ lại để đáp ứng nhu cầu<demand>
-   ### Pods and best practices

    -   Pods đáng tin cậy vgaf có thể tự động bắt đầu lại nếu chúng lỗi
-   ### Pods và thực tế nhất

        Use pods to group related containers together.
        Use services to expose pods to the outside world.
        Use network policies to control how pods communicate with each other.
        Use PodSecurityPolicies to restrict the capabilities of pods.
        Use secrets to store sensitive data.
        Use volumes to share data between pods.
        Use replicas to make your pods more resilient.
        Use health checks to ensure that your pods are healthy.
        Use logging and monitoring to track the health of your pods.

![Alt text](k8s/folder%20image/download.jpg)

-   ### POD là gì? 
    - là thành phần nhỏ nhất của k8s
    - abstraction over containers, cung cấp một lớp quản lý bổ sung cho các container, Điều này cho phép kubernetes quản lý các Pod thay vì các container trực tiếp và cung cấp tính linh hoạt hơn trong việc triển khai và quản lý các ứng dụng. => Kube quản lý Pod thôi, Pod quản lí container
    - Pod có thể chứa 1 hoặc nhiều container và container trong cùng một Pod sẽ chia sẻ `tài nguyên lưu trữ và mạng`
