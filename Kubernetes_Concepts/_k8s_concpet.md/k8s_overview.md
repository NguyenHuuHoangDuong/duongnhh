- ### Master note
  -   Chịu trách quản lí K8s Cluster.
  -   4 component: <kube API, Controller Manager, scheduler, etcd>
  -   <kube controller: access control, replication,>
        + Kube API Server: điểm vào chính quản lý các kubernetes Cluster. Tương tác với Kubernetes API. Frontend Kubernetes control plane.
        + Scheduler: Giám sát các pods, chưa được gán cho các node cụ thể nào. Theo dõi biến đổi với tài nguyên và thực hiện hành động để đảm bảo rằng cụm ở trạng thái nhất quán
        + Control Manager: chạy các controllers. Chúng được coi là background thread<tạo thêm chương trình không liên quan đến giao diện> chạy các task bên trong cluster. COntroller đảm nhiệm nhiều vai trò khác nhau, nhưng tất cả được complied thành một single binary. Vai trò controller bao gồm:
          + <Node controller> chịu trách nhiệm cho các trạng thái (worker state)
          + <replication> chịu trách nghiệm đảm bảo duy trì các pod sao cho đúng số lương
          + <endpoint> kết nối luôn được cập nhật, services <->Pods
          + <Service account và token>: Đảm bảo được tạo và xóa một cách chính xác <access manager> 

- ### ETCD
    - etcd là một simple distributed key value sotre <lưu trữ, quản lí dữ liệu, state, super data !!! distributed popular>
    - Một vài thông tin có thể lưu trữ ở đây là: job scheduling info, Pod detail, stage info, etc ...
- ### KUBECTL
    - interact master node use kubectl application, kubectl
    - kubectl có config file là kubeconfig. 
    - kubeconfig: server info, authen, để connect API Server
- ### Worker node
    - nơi ứng dụng được triển khai: worker <communicate back> master node
      - giáo tiếp <worker node> được xử lý bởi kubelet. <Kubelet> là một agent giao tiếp với API Server để xem liệu Pods đã được cho vào Node hay chưa
      - <kubelet execute pod containers> thông qua <container engine>  
      - Mount và run pod volume, secrets. overseeing state Pod của node và respond to Master.
      - Docker là một container native platform use for kubelet

- ### Kubeproxy 
      - <Network-proxy, load balancer> cho dịch vụ, trên một single worker node. Nó đảm nhiệm network routing cho TCP và UDP packets, thực hiện connecting forwarding
      - 1 hoặc nhiều container được nối trong pod. Pod là unit nhỏ nhất có thể được scheduled như một deployment trong K8s. Nhóm container trong pod dùng chung storage, linux namespace, ip address
      - khi pod deploy và running,, kubelet process giao tiếp với Pods để check state, health. kube-proxy sẽ route mọi packets tới Pods từ resource khác muốn communicate với chúng. worker node có thể 